# ALERTS — Regole (demo)

## Alert types
- `BLOCCATA`
- `SCADENZA_IMMINENTE`
- `DOCUMENTI_MANCANTI`
- `INATTIVA`
- `DOC_FORNITORE_IN_SCADENZA`

## Regole consigliate (semplici ma efficaci)
### 1) BLOCCATA
Vera se almeno una condizione:
- `nota_ultimo_step` contiene (case-insensitive): "MANCA", "FARE", "FERMA", "SOLLECIT", "NON PROCEDERE"
- fase è `IN_ATTESA` da > 7 giorni
- manca un documento obbligatorio per la tipologia e fase >= `IN_GESTIONE`

### 2) SCADENZA_IMMINENTE
- se `termine_presentazione_offerte` è valorizzata
- e oggi è entro N giorni (default 7) dalla scadenza
- e fase non è `ORDINATA`/`COMPLETA`

### 3) INATTIVA
- nessun evento in timeline da > X giorni (default 10)  
  (escludi pratiche già `COMPLETA`)

### 4) DOCUMENTI_MANCANTI
- in base a tipologia + fase (vedi WORKFLOW.md)  
  Esempio: in `ORDINATA` devono esserci ODA/RDO e ordinativo.

### 5) DOC_FORNITORE_IN_SCADENZA
- nel Document Vault: DURC/INAIL con valid_to entro 14 giorni
- genera alert di tipo “fornitore”, visibile in dashboard

## UI
Ogni alert deve mostrare:
- severità (alta/media/bassa)
- motivo (testo breve)
- “azioni suggerite” (es. “carica DURC”, “sollecita ordinativo”, “completa stipula”)

