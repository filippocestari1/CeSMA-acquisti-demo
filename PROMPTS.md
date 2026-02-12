# PROMPTS — Sequenza “pronta” per Codex (esegui in ordine)

> Modalità consigliata in Codex: **Code** (per applicare modifiche).  
> Dopo ogni prompt: controlla diff + esegui test/build + commit.

---

## Prompt 1 — Scaffold progetto + Auth + DB
Leggi `SPEC.md`, `AGENTS.md`.  
Crea una web app demo con:
- Next.js (App Router) + TypeScript
- Prisma + SQLite
- Tailwind + shadcn/ui
- Auth semplice (NextAuth credentials) con ruoli (RBAC)

Crea schema DB per:
- User, Role
- Supplier
- PurchaseRequest (Pratica)
- Attachment (file pratica)
- SupplierDocument (Vault)
- TimelineEvent (audit)

Aggiungi:
- README (run, migrate, seed)
- seed fake (nessun dato reale)
- test minimi (smoke)

---

## Prompt 2 — Importer Excel (opzionale)
Implementa uno script `scripts/import_excel.ts` (o python) che importa il foglio “ACQUISTI 2023” secondo `IMPORT_EXCEL.md`.  
Deve:
- normalizzare tipologia
- normalizzare SI/NO
- creare supplier + pratica
- scrivere timeline event “import”

Aggiungi comando `npm run import:excel -- data/file.xlsx`.

---

## Prompt 3 — Dashboard unica (split view)
Implementa schermata `/dashboard`:
- KPI cards (conteggi per fase + bloccate + scadenze)
- tabella pratiche con filtri
- layout master/detail: click su riga → dettaglio a destra
- badge alert (da alert engine)

---

## Prompt 4 — Dettaglio pratica + timeline + allegati
Nel pannello dettaglio:
- summary (campi principali)
- tab “Timeline” (chi/quando/cosa)
- tab “Allegati” (upload + download)
- tab “Note” (commenti)

RBAC:
- Richiedente: edit solo campi richiesta + allegati
- Operatore: edit tutto + change fase

---

## Prompt 5 — Alert engine
Implementa `lib/alerts` secondo `ALERTS.md`:
- calcolo alert per pratica (runtime, o materializzato in tabella)
- calcolo alert per documenti fornitore in scadenza
- UI: vista “Solo alert” + badge severità + motivazione + azioni suggerite

---

## Prompt 6 — Document Vault Fornitore
Schermata fornitori:
- lista fornitori
- dettaglio con documenti (DURC/INAIL ecc) con validità
Nella pratica:
- “Aggiungi DURC valido dal vault” (link o copia)

---

## Prompt 7 — PNRR mode + regole
Aggiungi campi PNRR (flag + campi dedicati) e validazioni:
- se pnrr=true → CUP obbligatorio
- dashboard filtro “Solo PNRR”
- checklist documentale più stringente

---

## Prompt 8 — Export CSV + audit hardening
- export CSV filtrato
- audit diff per modifiche campo (vecchio/nuovo)
- test e2e minimo (Playwright: login → dashboard → crea pratica → cambia fase)

