# CeSMA Acquisti — Codex Starter Pack (demo)

Questo pacchetto contiene file pronti da mettere **nella root del repo** per guidare Codex a costruire una **demo web** che replica il foglio Excel “Archivio Acquisti” e aggiunge i “plus” richiesti:
- dashboard unica con situazione generale + master/detail ordine
- audit trail (chi/quando/cosa)
- alert (pratiche bloccate, scadenze imminenti, documenti mancanti)
- gestione allegati + “document vault” per DURC/INAIL ecc riutilizzabili
- flussi per PNRR + tipologie di acquisizione CeSMA

Data riferimento: 12/02/2026

## Come usarlo con Codex (barra sinistra di ChatGPT)
1. Crea un repo (es. `cesma-acquisti-demo`) e copia questi file nella root.
2. Apri **Codex** dal menu a sinistra → collega GitHub → seleziona il repo.
3. Esegui i prompt in `PROMPTS.md` **in ordine** (uno per volta).  
   Dopo ogni step: controlla diff, avvia test/build, fai commit.

> Suggerimento: in demo usa SQLite; in produzione Postgres + SSO + storage documenti su S3/SharePoint.

---

## Cosa c’è dentro
- `SPEC.md` requisiti completi della demo (MVP + plus)
- `AGENTS.md` regole operative per Codex (niente dati reali, test, stile)
- `DATA_DICTIONARY.md` mapping Excel → campi app
- `WORKFLOW.md` stati, azioni, regole per tipologie (MePA / fuori MePA / estero / PNRR)
- `ALERTS.md` regole alert (bloccate, scadenze, doc mancanti, inattività)
- `RBAC.md` ruoli/privilegi (chi può vedere/modificare cosa)
- `UI_WIREFRAMES.md` schermate e componenti
- `PROMPTS.md` sequenza prompt “pronta” per Codex
- `IMPORT_EXCEL.md` come importare l’Excel (opzionale nella demo)

