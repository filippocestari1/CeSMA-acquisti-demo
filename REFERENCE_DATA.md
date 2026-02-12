# REFERENCE_DATA — Tipologie acquisto (normalizzazione)

Dal foglio Excel risultano varianti di scrittura (maiuscole/minuscole).  
Normalizza così:

- ODA MePA / ODA MEPA / ODA Mepa / OdA MePA → `ODA_MEPA`
- ODA CONVENZIONE → `ODA_CONVENZIONE`
- RDO-TD MePA / RDO-TD MEPA / RDO-TD MePA+X92 → `RDO_TD_MEPA`
- RDO-confronto di preventivi MePA → `RDO_CONFRONTO_PREVENTIVI_MEPA`
- TD fuori MePA / TD FUORI MEPA / TD fuori mepa / TD fuori Mepa / TD fuori MEPA → `TD_FUORI_MEPA`
- TD fuori MePA (DOPO RACCOLTA DI PREVENTIVI) → `TD_FUORI_MEPA_POST_PREVENTIVI`

Consiglio: salva anche `tipologia_raw` (testo originale) per tracciabilità.

