# AGENTS — Regole per Codex (CeSMA Acquisti)

## Regole dure (non negoziabili)
1. **NON usare dati reali** (nomi, email, PIVA, CIG/CUP reali).  
   Se servono esempi, usa dati fittizi e chiaramente “demo”.
2. UI e testi **in italiano**.
3. Ogni PR/task deve:
   - aggiornare README
   - includere test minimi o motivare perché non servono
4. Prima di introdurre dipendenze “pesanti” (es. sistemi notifiche complessi, servizi esterni):
   - spiega alternativa semplice
   - chiedi conferma nel commento del diff
5. Struttura modulare:
   - `domain/` (regole e tipi)
   - `db/` (schema/migrazioni)
   - `app/` (UI)
   - `lib/` (utilità: alert engine, auth, storage)
6. Calcoli “Excel-like” (latenza, working time) devono essere fatti lato server e testati.

## Standard qualità
- Niente “magia” non documentata: ogni feature deve essere tracciabile in SPEC.
- Error handling: messaggi chiari, mai stacktrace all’utente.
- Access control: enforce lato server, non solo UI.

