# WORKFLOW — Stati, tipologie, checklist

## 1) Stati (fase) — enum consigliato
- `BOZZA`
- `RICEVUTA_RDA`
- `DA_AVVIARE` (non ancora partita / in coda)
- `IN_GESTIONE` (in lavorazione)
- `IN_ATTESA` (manca input/documento/azione esterna)
- `ORDINATA` (ordine inviato / stipula completata)
- `IN_CONSEGNA` (DDT/Consegna in corso)
- `COLLAUDATA` (collaudo/conformità ricevuti)
- `FATTURATA`
- `PAGATA` (se gestite info pagamenti)
- `COMPLETA` (chiusa)

> Il testo Excel “STATO DI AVANZAMENTO” resta come `nota_ultimo_step` (multilinea).
> La UI mostra anche tag automatici: “MANCA…”, “FARE…”, “SOLLECITI…”.

## 2) Tipologie (normalizzate)
- `ODA_MEPA`
- `ODA_CONVENZIONE`
- `RDO_TD_MEPA`
- `RDO_CONFRONTO_PREVENTIVI_MEPA`
- `TD_FUORI_MEPA`
- `TD_FUORI_MEPA_POST_PREVENTIVI`
- `ACQUISTO_ESTERO` (opzionale)

## 3) Checklist documentale per tipologia (demo)
### ODA_MEPA
Obbligatori:
- richiesta/proposta (RDA o modulo interno)
- ODA (PDF)
- schede tecniche + prezzi (se applicabile)
- ordinativo/pagamento (quando disponibile)
- fattura (quando disponibile)
- DURC (se richiesto dalla tipologia/fornitore)

### RDO_TD_MEPA / RDO_CONFRONTO_PREVENTIVI
Obbligatori:
- RDO/TD (PDF)
- offerte ricevute (almeno 1)
- verbale/criterio aggiudicazione (se richiesto)
- ordinativo / stipula
- fattura (quando disponibile)
- DURC/INAIL (se richiesto)

### TD_FUORI_MEPA
Obbligatori:
- motivazione (campo)
- preventivo / dichiarazione unicità
- ordinativo / determina (se applicabile)
- fattura
- DURC/INAIL (se richiesto)

## 4) PNRR (flag `pnrr=true`)
Regole demo:
- CUP obbligatorio
- motivazione + tracciabilità più stringenti (campo note PNRR)
- dashboard: filtro rapido “Solo PNRR”
- eventuale “linea PNRR”: Missione, Componente, Investimento (campi testo)

