# DATA MANAGEMENT PLAN: SIDE QUEST - MAIN QUEST (SQMQ)

- **Progetto**: _Side Quest - Main Quest : visualizzazione e analisi geospaziale delle chiese di Roma_
- **Corso**: DHDMCH – Digital Humanities & Digital Cultural Heritage, a.a. 2024-2025
- **Autore**: Esther Montserrat Giordano, (https://orcid.org/0009-0000-3672-376X), Università di Bologna
- **Licenza dei dati**: [![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC_BY--SA_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)
- **Ultimo aggiornamento**: 16-07-2024

## Indice

- [Sommario Esecutivo](#sommario-esecutivo)
- [Introduzione](#introduzione)
- [Descrizione dei dati](#descrizione-dei-dati)
- [Documentazione e qualità dei dati](#documentazione-e-qualità-dei-dati)
- [Backup e Archiviazione](#backup-e-archiviazione)
- [Requisiti legali ed etici](#requisiti-legali-ed-etici)
- [Condivisione dei dati e conservazione a lungo termine](#condivisione-dei-dati-e-conservazione-a-lungo-termine)


## Sommario Esecutivo

Questo Data Management Plan descrive le modalità di gestione, documentazione, conservazione e condivisione dei dati prodotti per il progetto **_Side Quest - Main Quest (SQMQ)_**, incentrato sulla visualizzazione e analisi geospaziale delle chiese di Roma. Il progetto aderisce ai principi **FAIR** (_Findable, Accessible, Interoperable, Reusable_) e privilegia strumenti e formati **open source**.

## Introduzione

SQMQ nasce per esplorare l’interazione tra geografia, storia urbana e dati culturali. Utilizza un dataset storico integrato con coordinate geografiche moderne per analizzare e visualizzare la distribuzione delle chiese romane, attraverso strumenti come QGIS e Kepler.gl.

## Descrizione dei dati

* **Fonte principale**: *Diego Angeli, Le Chiese di Roma* (1922)
* **Dati aggiuntivi**: coordinate geografiche tramite Nominatim (OpenStreetMap), arricchimenti storici da Wikipedia/Wikidata
* **Formato dati**: `.CSV`, `.JSON`, `.TXT`, `.QGZ`, `.PNG`
* **Contenuto**:

  * Identificativi univoci per ogni chiesa
  * Coordinate geografiche (EPSG:4326)
  * Status attuale delle chiese (`Attiva`, `Demolita`, `Sconsacrata`, `NA`)
  * Metadati di base (consulta lo specifico [README](../data/CSV/README.md) per maggiori informazioni)

* **Struttura repo**:

  * [`/data/`](../data/): CSV e fonti grezze
  * [`/docs/`](/docs/): documentazione
  * [`/kepler/`](../kepler/): configurazioni e immagini interattive
  * [`/qgis/`](../kepler/): analisi spaziali 
  * [`/tutorials/`](../tutorials/): guide operative

## Documentazione e qualità dei dati

* Tutti i dataset sono documentati nei README delle rispettive cartelle
* Il dataset principale è stato pulito manualmente con **LibreOffice Calc**, in particolare:

  * Eliminazione di record privi di coordinate
  * Revisione dei campi testuali
  * I campi sono normalizzati per garantire consistenza (es. `Status_Attuale` = `“Attiva”`, `“Sconsacrata”`, `“Demolita”`, `“NA”`)
  * I file sono forniti in **formati aperti e interoperabili** (CSV, JSON )

## Backup e Archiviazione

* I dati sono versionati e archiviati su **GitHub**, con tracciabilità completa delle modifiche
* Per il backup a lungo termine è stato realizzato l'upload dei dataset versionati su [**Zenodo**](https://zenodo.org/records/15918009)
* È stato realizzato anche un backup su pendrive usb e sul Google Drive personale
* Tutti i file sono organizzati in sottocartelle chiare per tipo e scopo


## Requisiti legali ed etici

* Le fonti utilizzate sono **di pubblico dominio** (Angeli 1922) o **rilasciate con licenze compatibili** (Wikipedia: CC BY-SA 4.0)
* Le coordinate sono state ottenute da **OpenStreetMap/Nominatim**, che consente l’uso libero dei dati con attribuzione
* Nessun dato personale o sensibile è stato incluso


## Condivisione dei dati e conservazione a lungo termine

* I dati saranno resi pubblici tramite:

  * [**GitHub**](https://github.com/malemg/sqmq_project) per la collaborazione e la documentazione attiva
  * [**Zenodo**](https://zenodo.org/records/15918009) per l’archiviazione accademica e la generazione di DOI

* Il progetto utilizza licenza [**CC BY-SA 4.0**](https://creativecommons.org/licenses/by-sa/4.0/deed.it), che permette riuso, anche commerciale, con obbligo di attribuzione e condivisione nella stessa licenza

* I dati sono pubblicati con l’intento di promuovere la **replicabilità delle analisi**, l’**uso didattico** dei dati storici urbani. 

* I [dataset CSV principali](../data/CSV/) sono distribuiti anche in versioni con il numero esplicito di release (`v1.0`) nel nome file. 
  Questa strategia assicura:
  - La stabilità e la tracciabilità della versione esatta usata nel progetto.
  - La possibilità di preservare e condividere versioni aggiornate senza compromettere la riproducibilità.
  - L’aderenza ai principi FAIR per una condivisione dei dati trasparente e facilmente rintracciabile nel tempo.



