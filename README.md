# Atlante Fenotipico di Comunità

Sito web interattivo per esplorare l'*Atlante Fenotipico di Comunità* della comunità di Pollica: una griglia 3D di schede fotografiche fronte-retro, da scorrere, aprire e girare.

È una pagina statica, senza build e senza dipendenze da installare. La grafica usa [three.js](https://threejs.org/) (r184), caricato da CDN come modulo ES.

## Come provarlo in locale

Le immagini non si caricano aprendo `index.html` direttamente (`file://`): serve un server web.

```bash
python3 -m http.server 8000
```

Poi apri <http://localhost:8000>. Va bene anche `npx http-server .` (porta 8080).

Per il ricaricamento automatico a ogni salvataggio: `npm run dev` (usa `live-server`, si apre da solo il browser).

## Come si usa

| Azione | Effetto |
| --- | --- |
| Trascina | Esplora la griglia |
| Rotella / pinch | Avvicina e allontana |
| Click su una scheda | La apre; un altro click la gira (fronte ↔ retro) |
| `←` `→` `↑` `↓` | Soggetto precedente / successivo (con una scheda aperta) |
| `S` | Scorrimento automatico, si ferma con `S` o `Esc` |
| `?` | Mostra o nasconde l'elenco dei comandi |
| `Esc` | Chiude la scheda aperta |

Sul mobile ci sono i pulsanti nel riquadro in basso al posto dei tasti.

## Struttura del progetto

```
index.html     struttura della pagina e importmap di three.js
style.css      stile (interfaccia, schermata di caricamento, legenda)
main.js        scena 3D, caricamento, navigazione, input
images/        immagini a piena risoluzione (001.webp … 226.webp)
thumbs/        miniature JPG usate nella griglia; thumbs/pannelloni/ per i pannelloni
fonts/         Newsreader e Hanken Grotesk (interfaccia)
*.otf          LaLuxes (solo schermata di caricamento) e Humane (non usato)
```

## Come funziona

- **Griglia:** 15 × 10 celle. Ogni soggetto è una carta con due piani: fronte e retro. Le immagini sono numerate in coppia: soggetto *s* → fronte `2s+1`, retro `2s+2`.
- **Pannelloni:** quattro immagini grandi che occupano più celle (`PANNELLONI` in `main.js`). Si vedono nella griglia ma non si aprono né si girano.
- **Caricamento:** all'avvio si caricano solo le miniature dei fronti. La versione a piena risoluzione e il retro vengono caricati quando apri una carta e liberati quando la chiudi, per tenere bassa la memoria video.
- **Prestazioni:** i retri sono nascosti finché la carta non si apre. Il rendering si sospende quando la scena è ferma e riparte a ogni input. La leggera fluttuazione della griglia c'è solo su desktop, con input recente, e si smorza da sola.

## Configurazione

I parametri principali sono nell'oggetto `CFG` in cima a `main.js`: dimensioni della griglia, limiti dello zoom, velocità di navigazione e del marquee, ampiezza e durata della fluttuazione.

## Aggiungere o cambiare immagini

1. Metti le immagini a piena risoluzione in `images/` con nome a tre cifre (`001.webp`, `002.webp` …) e le miniature `.jpg` in `thumbs/` con lo stesso numero.
2. Aggiorna `TOTAL_IMGS` e `NUM_SUBJECTS` in `CFG` (immagini totali e soggetti = immagini / 2).
3. Per i pannelloni, modifica `PANNELLONI` e aggiungi la miniatura in `thumbs/pannelloni/` come `<nome> <colonne>x<righe>.jpg`.
