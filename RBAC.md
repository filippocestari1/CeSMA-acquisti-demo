# RBAC — Ruoli e privilegi (demo)

## Ruoli
- Admin
- Operatore CeSMA
- Responsabile/Dirigente
- Richiedente
- Auditor/Viewer

## Permessi principali
### Pratiche
- Create: Richiedente, Operatore, Admin
- Read:
  - Operatore/Admin/Responsabile/Auditor: tutte
  - Richiedente: solo proprie (o del proprio laboratorio, se configurato)
- Update campi:
  - Richiedente: solo campi “richiesta” (oggetto, caratteristiche, motivazioni, allegati, note)
  - Operatore/Admin: tutti i campi
  - Responsabile: campi approvazione + commenti
- Change fase:
  - Operatore/Admin
  - Responsabile: solo transizioni approvazione (se previste)
- Delete: solo Admin (o soft-delete)

### Document Vault (fornitori)
- Operatore/Admin: CRUD
- Richiedente: read + “richiedi caricamento” (opzionale)
- Auditor: read

### Export
- Operatore/Admin/Responsabile/Auditor: export CSV
- Richiedente: export solo proprie

> Nota: enforcement lato server (API), non solo UI.

