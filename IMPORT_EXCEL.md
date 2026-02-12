# IMPORT_EXCEL — Import (opzionale nella demo)

Obiettivo: importare dal foglio Excel “ACQUISTI 2023” i campi base.

## Strategia demo (semplice)
1. Copia l’Excel nella cartella `./data/` del progetto (es. `data/archivio_acquisti_2023.xlsx`)
2. Script di import:
   - legge la prima riga come header
   - normalizza SI/NO
   - normalizza tipologia acquisto (enum)
   - crea/aggiorna Fornitore (da “SOCIETA SCELTA” + PIVA)
   - crea Pratica
   - salva eventuali note (colonna A → flag_interno)
3. Non importare file allegati (in Excel sono solo riferimenti); in demo li carichi manualmente.

## Calcoli
- `latenza_giorni`:
  - se fase == DA_AVVIARE / IN_ATTESA e non esiste “data_avvio” → oggi - data_rda
- `tempo_lavorazione_giorni`:
  - se data_ordinativo presente → data_ordinativo - data_rda

## Nota
Nel file Excel originale alcune colonne sono formule. Se leggi l’xlsx devi usare i valori calcolati (cached values) o ricalcolare lato script.

