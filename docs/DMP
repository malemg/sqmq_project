# DATA MANAGEMENT PLAN: SIDE QUEST - MAIN QUEST (SQMQ)

- **Progetto**: _Side Quest - Main Quest : visualizzazione e analisi geospaziale delle chiese di Roma_
- **Corso**: DHDMCH – Digital Humanities & Digital Cultural Heritage, a.a. 2024-2025
- **Autore**: Esther Montserrat Giordano, (https://orcid.org/0009-0000-3672-376X), Università di Bologna
. **Licenza dei dati**: CC BY-SA 4.0
- **Ultimo aggiornamento**: 15-07-2024

## Indice

- [Sommario Esecutivo](#sommario-esecutivo)
- [Introduzione](#introduzione)
- [Descrizione dei dati](#descrizione-dei-dati)
- [Documentazione e qualità dei dati](#documentazione-e-qualità-dei-dati)
- [Backup e Archiviazione](#backup-e-archiviazione)
- [Requisiti legali ed etici](#requisiti-legali-ed-etici)
- [Condivisione dei dati e conservazione a lungo termine](#condivisione-dei-dati-e-conservazione-a-lungo-termine)


## 1. Sommario Esecutivo

Questo Data Management Plan descrive le modalità di gestione, documentazione, conservazione e condivisione dei dati prodotti per il progetto **_Side Quest - Main Quest (SQMQ)_**, incentrato sulla visualizzazione e analisi geospaziale delle chiese di Roma. Il progetto aderisce ai principi **FAIR** (_Findable, Accessible, Interoperable, Reusable_) e privilegia strumenti e formati **open source**.

## 2. Introduzione

SQMQ nasce per esplorare l’interazione tra geografia, storia urbana e dati culturali. Utilizza un dataset storico integrato con coordinate geografiche moderne per analizzare e visualizzare la distribuzione delle chiese romane, attraverso strumenti come QGIS e Kepler.gl.

## 3. Descrizione dei dati

* **Fonte principale**: *Diego Angeli, Le Chiese di Roma* (1922)
* **Dati aggiuntivi**: coordinate geografiche tramite Nominatim (OpenStreetMap), arricchimenti storici da Wikipedia/Wikidata
* **Formato dati**: CSV (raw e pulito), GPKG, JSON, TXT
* **Contenuto**:

  * Identificativi univoci per ogni chiesa
  * Coordinate geografiche (EPSG:4326)
  * Status attuale delle chiese (Attiva, Demolita, Sconsacrata, NA)
  * Metadati storici di base ( COMPILA )

* **Struttura repo**:

  * `/data/`: CSV e fonti grezze
  * `/qgis/`: analisi spaziali (project file `.qgz`, output `.gpkg`, risultati NNA)
  * `/kepler/`: configurazioni e immagini interattive
  * `/docs/`: documentazione
  * `/tutorials/`: guide operative

## 4. Documentazione e qualità dei dati

* Tutti i dataset sono documentati nei README delle rispettive cartelle
* Il dataset principale è stato pulito manualmente con **LibreOffice Calc**, in particolare:

  * Eliminazione di record privi di coordinate
  * Revisione dei campi testuali
  * I campi sono normalizzati per garantire consistenza (es. status = “Attiva”, “Sconsacrata”, “Demolita”, “NA”)
  * I file sono forniti in **formati aperti e interoperabili** (CSV, JSON, GPKG)

## 5. Backup e Archiviazione

* I dati sono versionati e archiviati su **GitHub**, con tracciabilità completa delle modifiche
* Per il backup a lungo termine è previsto l’upload finale su **Zenodo**, che fornirà un DOI persistente
* È stato realizzato anche un backup su pendrive usb e sul Google Drive personale
* Tutti i file sono organizzati in sottocartelle chiare per tipo e scopo


## 6. Requisiti legali ed etici

* Le fonti utilizzate sono **di pubblico dominio** (Angeli 1922) o **rilasciate con licenze compatibili** (Wikipedia: CC BY-SA 4.0)
* Le coordinate sono state ottenute da **OpenStreetMap/Nominatim**, che consente l’uso libero dei dati con attribuzione
* Nessun dato personale o sensibile è stato incluso


## 7. Condivisione dei dati e conservazione a lungo termine

* I dati saranno resi pubblici tramite:

  * **GitHub** per la collaborazione e la documentazione attiva
  * **Zenodo** per l’archiviazione accademica e la generazione di DOI
* Il progetto utilizza licenza **CC BY-SA 4.0**, che permette riuso, anche commerciale, con obbligo di attribuzione e condivisione nella stessa licenza
* I dati sono pubblicati con l’intento di promuovere la **replicabilità delle analisi**, l’**uso didattico** dei dati storici urbani. 
* I dataset CSV principali sono distribuiti anche in versioni con il numero esplicito di release (`v1.0`) nel nome file. 
  Questa strategia assicura:
  - La stabilità e la tracciabilità della versione esatta usata nel progetto.
  - La possibilità di preservare e condividere versioni aggiornate senza compromettere la riproducibilità.
  - L’aderenza ai principi FAIR per una condivisione dei dati trasparente e facilmente rintracciabile nel tempo.



