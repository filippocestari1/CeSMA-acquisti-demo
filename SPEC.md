# SPEC — Demo “CeSMA Acquisti” (da Excel a Web App con plus)

## 0) Obiettivo
Realizzare una **demo** web che:
1. Replica tutte le informazioni gestite oggi nel foglio Excel “Archivio Acquisti”.
2. Aggiunge **plus** operativi:
   - **Dashboard unica**: quadro generale + accesso rapido ai casi critici.
   - **Vista ordine**: stato pratica, chi/quando ha lavorato, timeline completa, allegati.
   - **Alert**: pratica bloccata, scadenze imminenti, documentazione mancante, inattività.
   - **Gestione documenti**: allegati per pratica + archivio documenti fornitore (es. DURC) riutilizzabile in 1 click.
   - **Flussi**: tipologie di acquisto CeSMA + gestione PNRR (campi obbligatori, controlli, checklist).

## 1) Ambito demo (MVP)
### 1.1 Funzionalità core
- CRUD pratiche/acquisti (creazione, modifica con permessi, ricerca, filtri, export CSV).
- Master/Detail “1 schermata”:
  - sinistra: tabella con filtri e indicatori (stato, alert, scadenze)
  - destra: dettaglio ordine con timeline + allegati + log
- Gestione stati “strutturata” + nota libera:
  - `fase` (enum) + `nota_ultimo_step` (testo multilinea, come Excel)
- Allegati per pratica (drag&drop + tag doc tipo DURC, Fattura, DDT, Collaudo, Preventivo…).
- Audit log: ogni modifica campo, cambio fase, upload file, commento.

### 1.2 Plus (devono esserci nella demo)
- **Alert engine** (vedi `ALERTS.md`) con:
  - bloccata (mancano azioni/doc o testo “MANCA/FARE”)
  - scadenza imminente (entro N giorni)
  - inattiva (nessuna lavorazione da X giorni)
  - doc fornitore scaduti / in scadenza (DURC ecc)
- **Document Vault Fornitore**
  - per ogni fornitore: DURC/INAIL/altro con validità (da–a)
  - in una pratica: “aggiungi DURC valido” → copia/collega documento in 1 click
- **PNRR mode**
  - flag `pnrr=true`
  - campi dedicati (es. Missione/Componente/Linea, CUP obbligatorio, riferimenti)
  - checklist e controlli differenziati

## 2) Ruoli e privilegi (demo)
- **Admin**: tutto (utenti, ruoli, configurazioni, reference data).
- **Operatore CeSMA**: gestisce pratiche, cambia fasi, completa checklist, vede tutto.
- **Responsabile/Dirigente**: approva/respingi, vede tutto, commenta.
- **Richiedente**: crea e vede le proprie pratiche, carica allegati, commenta; non può cambiare fasi “amministrative”.
- **Auditor/Viewer**: sola lettura + export.

Dettagli in `RBAC.md`.

## 3) Dati da gestire (derivano dall’Excel)
- Tutti i campi in `DATA_DICTIONARY.md` sono presenti nel form “Pratica”.
- Campi “calcolati” (latenza, tempo lavorazione) sono calcolati server-side e mostrati in UI.

## 4) Tipologie di acquisto CeSMA (demo)
- ODA MePA
- ODA Convenzione
- RDO / TD su MePA
- RDO (confronto preventivi su MePA)
- TD fuori MePA (anche dopo raccolta preventivi)
- Acquisto estero (se necessario)

Ogni tipologia ha:
- campi obbligatori
- documenti obbligatori
- scadenze tipiche (se applicabili)

Vedi `WORKFLOW.md`.

## 5) Dashboard unica (requisito chiave)
Widget minimi:
- Conteggi per fase (Da avviare / In lavorazione / In attesa / Completo)
- “Bloccate” (top 10 con motivo)
- “Scadenze entro 7/14 giorni”
- “Inattive da > X giorni”
- Ricerca full-text (prot RDA, richiedente, oggetto, fornitore, CIG/CUP)

## 6) Timeline pratica (chi/quando)
Per ogni pratica:
- lista eventi ordinati (creazione, modifiche, cambi fase, upload allegati, commenti)
- per ogni evento: utente, timestamp, tipo evento, diff sintetico

## 7) Requisiti non funzionali (demo)
- UI in italiano
- logging e audit
- test minimi (unit + smoke e2e)
- seed dati demo (fake)
- Docker opzionale

## 8) Tech stack suggerito per demo
Scelta consigliata:
- Next.js (App Router) + TypeScript
- Prisma + SQLite (demo) → switch facile a Postgres
- Auth: NextAuth (credentials per demo)
- Storage allegati: filesystem locale (demo) + interfaccia astratta per S3/SharePoint

