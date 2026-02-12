| Col | Campo Excel | Campo app (snake_case) | Tipo | Note / Validazioni |
|---|---|---|---|---|
| A | (senza intestazione) | flag_interno | string | Note interne tipo 'fatta', 'no cig', TODO; visibile solo CESMA/Admin |
| B | DATA RDA | data_rda | date |  |
| C | CONTATORE RDA/GIORNO | contatore_rda_giorno | int |  |
| D | PROT. RDA | prot_rda | string (generato) | ID umano: in Excel è calcolato; nell’app generalo come `ACYY_<YYYYMMDD>.<contatore> <richiedente>` o simile. |
| E | RESPONSABILE RDA | responsabile_rda | string |  |
| F | RICHIEDENTE | richiedente | string |  |
| G | LABORATORIO DI AFFERENZA DEL RESPONSABILE/RICHIEDENTE E/O PROGETTO DI RIFERIMENTO | laboratorio_di_afferenza_del_responsabile_richiedente_e_o_progetto_di_riferimento | string |  |
| H | STATO DI AVANZAMENTO  (ultimo step fatto) | stato_di_avanzamento_ultimo_step_fatto | enum + string | Testo libero: nell’app separa `fase` (enum) + `nota_ultimo_step` (testo). |
| I | TEMPO LATENZA (GG) PRIMA DI INIZIO  LAVORAZIONE tempo trascorso dalla ricezione rda alla data odierna (solo per acquisti non ancora avviati) | tempo_latenza_gg_prima_di_inizio_lavorazione_tempo_trascorso_dalla_ricezione_rda_alla_data_odierna_solo_per_acquisti_non_ancora_avviati | date? |  |
| J | TEMPO DI LAVORAZIONE (GG)  (data ordinativo - data rda) | tempo_di_lavorazione_gg_data_ordinativo_data_rda | date? |  |
| K | NUMERO ORD PAGAMENTO | numero_ord_pagamento | string |  |
| L | DATA ORDINATIVO | data_ordinativo | date |  |
| M | CIG | cig | string | Validazione formato (non bloccare in demo, ma segnala). |
| N | DICHIARAZIONE COLLAUDO | dichiarazione_collaudo | string |  |
| O | CUP | cup | string | Validazione formato (non bloccare in demo, ma segnala). |
| P | PREVENTIVO e/ o dichiarazione unicità | preventivo_e_o_dichiarazione_unicita | string |  |
| Q | IMPORTO ORDINATIVO AL NETTO DI IVA | importo_ordinativo_al_netto_di_iva | money |  |
| R | IMPORTO IVA | importo_iva | money |  |
| S | IMPORTO TOTALE LORDO | importo_totale_lordo | money |  |
| T | OGGETTO DELLA SPESA | oggetto_della_spesa | string |  |
| U | CARATTERISTICHE TECNICHE DELLE FORNITURE/SERVIZI | caratteristiche_tecniche_delle_forniture_servizi | string |  |
| V | FONDO  | fondo | string | Collega a 'Progetto/Fondo' (anche PNRR). |
| W | MOTIVAZIONI | motivazioni | string | Campo obbligatorio per alcune tipologie (es. TD fuori MePA). |
| X | TIPO DI ACQUISTO | tipo_di_acquisto | enum | Normalizza: ODA MEPA, ODA CONVENZIONE, RDO/TD MEPA, RDO (confronto preventivi), TD FUORI MEPA, ecc. |
| Y | N TRATTATIVA | n_trattativa | string |  |
| Z | data oda/rdo | data_oda_rdo | date |  |
| AA | TERMINE PRESENTAZIONE OFFERTE | termine_presentazione_offerte | date | Usato per alert 'scadenza imminente'. |
| AB | BENI INFORMATICI | beni_informatici | bool | Normalizza SI/NO, si/no → boolean. |
| AC | BENI NON INFORMATICI > 5000 | beni_non_informatici_5000 | bool | Normalizza SI/NO, si/no → boolean. |
| AD | BENI NON INFORMATICI < 5000 | beni_non_informatici_5000 | bool | Normalizza SI/NO, si/no → boolean. |
| AE | CRITERIO DI AGGIUDICAZIONE | criterio_di_aggiudicazione | string |  |
| AF | SOCIETA CHE HANNO RISPOSTO | societa_che_hanno_risposto | string |  |
| AG | SOCIETA SCELTA | societa_scelta | string |  |
| AH | INDIRIZZO | indirizzo | string |  |
| AI | PIVA | piva | string |  |
| AJ | DOCUMENTAZIONE ODA | documentazione_oda | string |  |
| AK | DOCUMENTAZIONE RDO | documentazione_rdo | string |  |
| AL | SCHEDE TECNICHE CON PREZZI verbale di installazione | schede_tecniche_con_prezzi_verbale_di_installazione | string |  |
| AM | FATTURA | fattura | string |  |
| AN | DATA FATTURA | data_fattura | date |  |
| AO | DURC | durc | string | Nel foglio sono riferimenti; nell’app gestisci come allegati + scadenze/validità. |
| AP | INAIL ECC | inail_ecc | string | Nel foglio sono riferimenti; nell’app gestisci come allegati + scadenze/validità. |
| AQ | IL/LA PROF PROF.SSA | il_la_prof_prof_ssa | string |  |
| AR | DEL/DELLA | del_della | string |  |
| AS | RICHIESTA DEL PROFESSORE /DELLA PROFESSORESSA | richiesta_del_professore_della_professoressa | string |  |
| AT | NOTE | note | string |  |
| AU | N  DETERMINA  | n_determina | string/int |  |
| AV | DATA DETERMINA | data_determina | date |  |
| AW | RIFERIMENTI DDT | riferimenti_ddt | string |  |
| AX | DESTINAZIONE BENE | destinazione_bene | string | Suggerisci lista sedi/locazioni + testo libero. |