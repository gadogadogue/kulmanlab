---
title: LayerManager — Gestisci Tutti i Livelli in un'Unica Tabella
description: Il comando LayerManager apre una tabella con tutti i livelli del disegno, permettendoti di aggiungere livelli e modificare direttamente per ciascuno congelamento, blocco, stampa, colore, peso linea e tipo linea.
keywords: [layer manager, tabella livelli CAD, gestire livelli CAD, aggiungere livello CAD, congela blocca stampa livello, kulmanlab gestione livelli]
group: layer
order: 1
---

# LayerManager

Il comando `LayerManager` apre una tabella che elenca tutti i livelli del disegno, con le impostazioni **Freeze** (congela), **Lock** (blocca), **Plot** (stampa), **Colore**, **Peso linea** e **Tipo linea** modificabili direttamente nella riga. È il punto centrale per aggiungere nuovi livelli e regolare il comportamento di quelli esistenti — gli altri comandi dei livelli ([LayerMakeCurrent](../layer-make-current/), [LayerMatch](../layer-match/), [LayerIsolate](../layer-isolate/), [LayerUnfreezeAll](../layer-unfreeze-all/)) svolgono ciascuno un compito specifico senza aprirlo.

## Aprire il Gestore Livelli

- Digita `LayerManager` nel terminale, **oppure**
- Clicca il pulsante **Layer Manager** nel pannello dei livelli.

La finestra di dialogo si apre come pannello fluttuante; non serve selezionare nulla prima.

## La tabella dei livelli

| Colonna | Cosa controlla |
|---------|-----------------|
| Name | Il nome del livello, mostrato in sola lettura nella tabella (impostato una volta, alla creazione) |
| Freeze | Nasconde le entità del livello e le esclude dalla selezione finché non viene scongelato |
| Lock | Impedisce la modifica delle entità sul livello, senza nasconderle |
| Plot | Se le entità del livello sono incluse in stampa o nell'esportazione in PDF |
| Color | Il colore ACI del livello — clicca sul campione per aprire il selettore colore |
| Lineweight | Lo spessore linea del livello — clicca sul chip per aprire il selettore dello spessore |
| Linetype | Il motivo tratteggiato del livello — clicca sul chip per aprire il selettore del tipo linea |

Attivare o disattivare Freeze, Lock o Plot ha effetto immediato — non c'è un passaggio di salvataggio separato. Le entità impostate su **ByLayer** per colore, spessore linea o tipo linea (l'impostazione predefinita) adottano ciò che imposti qui; le entità con una propria sovrascrittura esplicita non vengono influenzate.

## Aggiungere un livello

1. Clicca **+ Add Layer** in fondo alla tabella.
2. Digita un nome e premi **Invio** per confermare, oppure **Escape** per annullare.

I nomi dei livelli possono contenere lettere, numeri, spazi e `_`, `-`, `$`. Un nome vuoto, già in uso, o con qualsiasi altro carattere viene rifiutato con un errore mostrato in linea, e la riga resta aperta per un altro tentativo.

I nuovi livelli iniziano **scongelati, sbloccati, stampabili**, con colore 7 (bianco/nero), spessore linea Default e tipo linea Continuous — le stesse impostazioni predefinite che [Import](../import/) assegna al livello `0` in un disegno vuoto.

## Cosa non puoi fare qui

Non c'è un pulsante per eliminare — i livelli non vengono mai rimossi una volta creati, solo congelati o lasciati inutilizzati. La tabella non indica nemmeno quale livello sia quello *corrente*; questo si imposta dal menu a discesa del pannello dei livelli o tramite [LayerMakeCurrent](../layer-make-current/), non da questa finestra di dialogo.

## Riferimento tastiera

| Tasto | Azione |
|-------|--------|
| `Invio` | Conferma il nome di un nuovo livello (durante l'aggiunta) |
| `Escape` | Annulla l'aggiunta di un livello, oppure chiude la finestra di dialogo |

## Comandi correlati

| Comando | Cosa fa |
|---------|---------|
| [LayerMakeCurrent](../layer-make-current/) | Imposta il livello attivo per corrispondere al livello dell'entità cliccata |
| [LayerMatch](../layer-match/) | Riassegna le entità selezionate al livello di un'entità sorgente |
| [LayerIsolate](../layer-isolate/) | Congela tutti i livelli tranne quelli delle entità selezionate |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | Scongela tutti i livelli in un solo passaggio |
