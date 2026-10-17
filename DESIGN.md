---
name: Atlante Fenotipico di Comunità
description: Una mappa di volti nell'oscurità: griglia 3D di schede fotografiche, interfaccia discreta e precisa.
colors:
  night-teal: "#06141b"
  tide-teal: "#2596be"
  ember-coral: "#ff9150"
  frost-ink: "#eafbff"
  pure-white: "#ffffff"
  signal-magenta: "#ee15ef"
typography:
  brand:
    fontFamily: "LaLuxes, Georgia, serif"
    fontSize: "clamp(.95rem, 2.4vw, 1.4rem)"
    fontWeight: 400
    lineHeight: 1.2
    letterSpacing: ".24em"
  display:
    fontFamily: "Newsreader, Georgia, 'Times New Roman', serif"
    fontSize: "1.7rem"
    fontWeight: 400
    lineHeight: 1.45
    letterSpacing: ".005em"
  label:
    fontFamily: "Hanken Grotesk, system-ui, sans-serif"
    fontSize: ".75rem"
    fontWeight: 500
    lineHeight: 1.45
    letterSpacing: ".2em"
  body:
    fontFamily: "Hanken Grotesk, system-ui, sans-serif"
    fontSize: ".95rem"
    fontWeight: 400
    lineHeight: 1.4
rounded:
  key: "6px"
  card: "14px"
  pill: "999px"
spacing:
  xs: ".2rem"
  sm: ".65rem"
  md: "1rem"
  lg: "1.6rem"
components:
  button-round:
    backgroundColor: "rgba(37,150,190,.12)"
    textColor: "{colors.tide-teal}"
    rounded: "{rounded.pill}"
    size: "40px"
  button-round-hover:
    backgroundColor: "rgba(255,145,80,.14)"
    textColor: "{colors.ember-coral}"
  button-flip:
    backgroundColor: "rgba(255,145,80,.12)"
    textColor: "{colors.ember-coral}"
    typography: "{typography.label}"
    rounded: "{rounded.pill}"
    height: "40px"
  legend-card:
    backgroundColor: "rgba(8,22,30,.96)"
    textColor: "{colors.frost-ink}"
    rounded: "{rounded.card}"
    padding: "1.6rem 1.8rem"
  legend-key:
    backgroundColor: "rgba(37,150,190,.12)"
    textColor: "{colors.tide-teal}"
    typography: "{typography.label}"
    rounded: "{rounded.key}"
    padding: ".2rem .5rem"
---

# Design System: Atlante Fenotipico di Comunità

## Overview

**Creative North Star: "La Mappa dei Volti"**

L'Atlante si attraversa come un territorio: una griglia 15 × 10 di ritratti che si trascina, si avvicina, si apre. Il fondo teal-notte è lo spazio della mappa; i volti sono il paesaggio e l'interfaccia è la legenda, mai l'attrazione. Il tono è scientifico e preciso, come in un atlante di ricerca: etichette ordinate, nessun gergo decorativo, nessuna enfasi gratuita.

Le persone ritratte sono reali, quindi l'interfaccia resta discreta: poche superfici, bordi sottili, testi piccoli ma leggibili. L'identità sta in tre cose fisse: il titolo in LaLuxes maiuscolo bianco, il teal come colore di sistema e un unico accento caldo che segnala l'azione.

**Key Characteristics:**
- Fondo unico `#06141b` che continua nella scena 3D, nella nebbia e nella vignetta.
- Chrome minimo: barra in alto con scrim sfumato, pulsanti a pillola con bordo teal.
- Un accento (corallo) per azione e stato attivo, uno secondario (magenta) per la navigazione tra soggetti.
- Serif per numeri e titoli di sezione, grottesco per etichette e comandi.

## Colors

Palette ristretta su fondo scuro: un neutro profondo, un teal di sistema, un accento caldo.

### Primary
- **Corallo Brace** (#ff9150): accento. Pulsante "Gira", stato attivo dello scorrimento automatico, anello di focus, titolo della legenda, hover dei comandi. Solo dove serve un'azione o uno stato.

### Secondary
- **Teal Marea** (#2596be): colore di sistema. Bordi e icone dei pulsanti, tasti nella legenda, etichette secondarie, particelle e griglia della scena.
- **Magenta Segnale** (#ee15ef): hover dei pulsanti di navigazione tra soggetti (‹ ›), per distinguerli dal resto.

### Neutral
- **Notte Teal** (#06141b): fondo del sito, del loader, della scena e della nebbia.
- **Ghiaccio** (#eafbff): testo principale, numeri e descrizioni.
- **Bianco** (#ffffff): titolo e sottotitolo dell'header.

### Named Rules
**The One Warm Voice Rule.** Il corallo è l'unico colore caldo e compare solo su azione, stato attivo o focus. Se è ovunque, non segnala più nulla.
**The Tinted Neutral Rule.** Nessun grigio: i secondari sono ink o teal con trasparenza, mai un grigio neutro.

## Typography

**Header Font:** LaLuxes (con Georgia). Solo titolo del sito e schermata di caricamento: è l'identità del progetto e non cambia.
**Display Font:** Newsreader (con Georgia). Numero della scheda e titolo della legenda.
**Body/Label Font:** Hanken Grotesk (con system-ui). Etichette, comandi e descrizioni.

**Character:** una voce d'archivio, serif per ciò che si legge come un nome o un numero, grottesco per ciò che si usa come comando. LaLuxes ha un solo peso e legature che rovinano le lettere: legature disattivate sempre, nessun grassetto sintetico.

### Hierarchy
- **Brand** (400, clamp(.95rem, 2.4vw, 1.4rem), 1.2, +.24em, maiuscolo, bianco): titolo del sito.
- **Display** (Newsreader 400, 1.6–1.7rem): numero della scheda aperta, titolo della legenda.
- **Body** (Hanken 400, .95rem, 1.4): descrizioni nella legenda.
- **Label** (Hanken 500, .75rem, +.14–.22em, maiuscolo): kind, sottotitolo, didascalie dei pulsanti, tasti.

### Named Rules
**The 12px Floor Rule.** Nessun testo funzionale sotto i 12px.
**The No Faux Bold Rule.** LaLuxes è solo 400: la gerarchia si fa con corpo, maiuscolo e spaziatura, non con `font-weight`.

## Layout

La scena riempie la finestra; il chrome è sovrapposto e si ritira. Barra in alto alta 64px (56 su mobile) con scrim sfumato; deck in basso alto 70px su mobile. Margini laterali `clamp(1rem, 4vw, 2.4rem)`. Sotto i 560px il titolo va su due righe, il sottotitolo sparisce e la scritta "Esc" nel dettaglio viene nascosta per far stare i comandi a 360px. Il deck ha due modalità: sfoglia (scrubber con frecce) e dettaglio (precedente, gira, numero, successivo, chiudi).

## Elevation & Depth

La profondità viene dallo spazio 3D: nebbia, vignetta radiale che quasi sparisce quando una scheda è aperta, piano scuro dietro le carte. Il chrome è piatto: scrim sfumato in alto, bordi sottili al posto delle ombre. L'unica ombra strutturale è quella della legenda (`0 24px 60px rgba(0,0,0,.5)`). Gli aloni colorati al hover dei pulsanti sono un residuo da ridurre.

### Named Rules
**The Flat Chrome Rule.** I comandi non hanno ombra a riposo: bordo e tinta bastano.

## Shapes

Pillole (999px) per i comandi, rettangoli arrotondati 14px per la legenda, 6px per i tasti. Cerchio per il pulsante `?` e per il cursore dello scrubber. Linee da 1px in teal al 22–40%; binario dello scrubber da 2px.

## Components

### Buttons
- **Shape:** pillola o cerchio (altezza 40px, minimo 40px di larghezza).
- **Default:** fondo teal al 12%, bordo teal al 40%, icona o testo teal.
- **Hover/Focus:** passa al corallo (fondo al 14%, bordo al 50%); i pulsanti ‹ › del dettaglio passano al magenta. Focus: anello corallo 2px.
- **Gira:** azione primaria del dettaglio, già in corallo (fondo 12%, bordo 45%) con icona e didascalia.
- **Chiudi:** fantasma, trasparente, testo ink al 55%.

### Scrubber
Binario 2px teal al 22% con riempimento sfumato teal→corallo e cursore corallo da 14px.

### Legend
Senza contenitore: nessun fondo, bordo o ombra, solo la velatura scura della scena. Titolo bianco in Newsreader, tasti in bianco 600 allineati a destra senza riquadro, descrizioni in ink al 55%. Nessun colore di palette nel pannello.

### Brand
Titolo LaLuxes bianco maiuscolo con sottotitolo "Comunità di Pollica" in Hanken bianco, su scrim sfumato.

## Do's and Don'ts

### Do:
- **Do** tenere `--accent` (#ff9150) solo su azioni, stati attivi e focus.
- **Do** mantenere l'header in LaLuxes maiuscolo bianco, con legature disattivate.
- **Do** usare tinte di ink o teal per i testi secondari, mai grigi.
- **Do** portare ogni nuovo comando ad almeno 40px di altezza e testo di almeno 12px.
- **Do** verificare ogni modifica a 360px di larghezza.

### Don't:
- **Don't** mettere nomi, didascalie o testi inventati sulle persone ritratte.
- **Don't** usare grassetti sintetici o pesi diversi da 400 con LaLuxes.
- **Don't** aggiungere un secondo accento caldo né usare il magenta fuori dalla navigazione.
- **Don't** coprire i volti: l'interfaccia non compete con le fotografie.
