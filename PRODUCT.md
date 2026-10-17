# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users
Tre pubblici, tutti in italiano: le persone della comunità di Pollica (chi compare nell'Atlante o lo conosce), i visitatori online (curiosi, studiosi, studenti, spesso da telefono) e il pubblico di una mostra o installazione fisica, dove il sito è mostrato su schermo grande o tablet. Il lavoro è sfogliare, riconoscere, aprire una scheda e leggerne il retro.

## Product Purpose
Sito interattivo per esplorare l'*Atlante Fenotipico di Comunità* di Pollica: una griglia 3D di 113 schede fotografiche fronte-retro (226 immagini) da scorrere, aprire e girare. Il fronte è un ritratto fotografico, il retro porta testi e dati sul soggetto. Successo: il visitatore esplora senza istruzioni, apre molte schede e si ferma a leggerle.

## Positioning
Non è una galleria di foto: è un atlante di persone reali di una comunità, ogni scheda ha un fronte (il volto) e un retro (la sua scheda di dati), da esplorare in uno spazio 3D continuo.

## Operating Context
Pagina statica senza build, grafica con three.js. Input a mouse, tastiera, tocco e pinch. Uso in mostra su schermo grande, online su desktop e telefono. Quattro pannelloni occupano più celle della griglia e non si aprono.

## Capabilities and Constraints
- Griglia 15 × 10; soggetto *s* ha fronte `2s+1` e retro `2s+2`.
- Caricamento economico in memoria video: miniature subito, piena risoluzione solo alla scheda aperta.
- Navigazione: trascina, rotella/pinch, click per aprire e girare, frecce, `S` per lo scorrimento automatico, `?` per i comandi, `Esc` per chiudere.
- Solo italiano, nessuna traduzione prevista.
- Deve funzionare bene su telefono, non solo su desktop.

## Brand Commitments
- Il carattere LaLuxes viene dall'identità del progetto e resta; l'header (titolo in LaLuxes maiuscolo, bianco) non deve cambiare.
- Gli altri font e i colori dell'interfaccia non sono vincolanti: possono cambiare.

## Evidence on Hand
Fotografie reali in `images/` (226 webp) con miniature in `thumbs/`. Non esistono testimonianze, dati o testi di contesto nel repository: non inventarne.

## Product Principles
- Le persone ritratte sono reali: nessun nome, didascalia o dato inventato, rispetto di consenso e privacy.
- L'immagine guida; l'interfaccia si ritrae e non compete con i volti.
- Si capisce da soli: i comandi si scoprono senza manuale, su mouse come su tocco.
- Lo stesso gesto funziona in mostra e sul telefono.

## Accessibility & Inclusion
Uso da telefono centrale; testo funzionale leggibile (mai sotto i 12px), contrasto adeguato, focus visibile da tastiera.
