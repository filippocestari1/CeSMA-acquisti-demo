# UI — Wireframes (demo)

## Schermata 1: Dashboard (unica)
Layout “split”:
- **Header**: ricerca globale + filtri rapidi (Solo bloccate / Solo PNRR / Scadenze 7g)
- **KPI cards**: conteggi per fase + importi (totale e per fondo, opzionale)
- **Master/Detail**
  - Colonna sinistra: tabella pratiche
    - colonne minime: Prot RDA, Data RDA, Richiedente, Fornitore, Tipologia, Fase, Badge alert, Scadenza
    - filtri: fase, tipologia, fondo, laboratorio, PNRR, “mancano doc”
  - Colonna destra: dettaglio pratica selezionata
    - summary (importo, CIG/CUP, fornitore, fondo)
    - timeline
    - allegati (con quick-add dal Vault)
    - note/commenti

## Schermata 2: Nuova/Modifica pratica
Form a sezioni:
1) Anagrafica (data RDA, responsabile, richiedente, laboratorio/progetto)
2) Spesa (oggetto, caratteristiche, motivazioni)
3) Tipologia e classificazioni (MePA/fuori MePA, beni informatici ecc)
4) Fornitore (ricerca o creazione)
5) Dati amministrativi (CIG, CUP, determina, ddt, destinazione)
6) Allegati (drag&drop + selezione da Vault)
7) PNRR (toggle + campi dedicati)

## Schermata 3: Fornitori + Document Vault
- lista fornitori
- dettaglio fornitore con documenti (DURC/INAIL ecc) + scadenze

## Schermata 4: Admin
- utenti e ruoli
- tabelle di riferimento (laboratori, fondi/progetti, sedi)

