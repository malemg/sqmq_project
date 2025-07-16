# SIDE QUEST - MAIN QUEST (SQMQ): visualizzazione e analisi geospaziale delle chiese di Roma


## Indice

1. [Introduzione](#1-introduzione)  
2. [Obiettivi e Pianificazione](#2-obiettivi-e-pianificazione)  
3. [Raccolta dei Dati](#3-raccolta-dei-dati)  
4. [Metodologia di Analisi](#4-metodologia-di-analisi)  
5. [Esempio di Ricerca](#5-esempio-di-ricerca)  
6. [Risultati e Visualizzazioni](#6-risultati-e-visualizzazioni)  
   - [6.1 Analisi descrittiva del dataset](#61-analisi-descrittiva-del-dataset)  
   - [6.2 Analisi spaziale: distribuzione e vicinanza](#62-analisi-spaziale-distribuzione-e-vicinanza)  
   - [6.3 Visualizzazioni interattive](#63-visualizzazioni-interattive)  
7. [Preservazione e Condivisione](#7-preservazione-e-condivisione)  
8. [Licenze e Riferimenti](#8-licenze-e-riferimenti)  
9. [Conclusioni](#9-conclusioni)  


## 1. Introduzione

Il progetto **SQMQ** si propone di esplorare la distribuzione geospaziale delle chiese di Roma presenti nella fonte storica di **Diego Angeli** (Diego Angeli, _Le Chiese di Roma_, Roma, Società Editrice Dante Alighieri, 1922), combinando informazioni storiche e coordinate moderne. 
L’intero processo si svolge nel rispetto dei principi **FAIR** (Findable, Accessible, Interoperable, Reusable) e fa uso di **strumenti e dati open-source**.


## 2. Obiettivi e Pianificazione

- Mappare le chiese cristiane di Roma indicate nella fonte di Angeli (1922), **nell’ordine della fonte originale** (alfabetico)
- Analizzare la **distribuzione spaziale**, **densità** e **collocazione urbana o periferica**
- Utilizzare strumenti liberi e accessibili per l’elaborazione: **QGIS**, **Kepler.gl**
- Integrare metadati e arricchimenti storici tramite **Wikipedia** e **Wikidata**
- Favorire la **continuità progettuale**, creando una base dati estensibile ad altre fonti simili


## 3. Raccolta dei Dati

### Dati geospaziali

Le coordinate geografiche e le informazioni descrittive sono state ottenute tramite:

- **OpenStreetMap**, con:
  - API **Nominatim** per la geocodifica

- Fonti aperte per verifica e arricchimenti: 
  - **Wikipedia** (identificazione, stato, demolizioni) 
  - **Wikidata** (eventuali URI o ID collegabili)


## 4. Metodologia di Analisi

1. Inserimento dei dati originali della fonte Angeli in foglio di calcolo (LibreOffice Calc)
2. Ricerca delle chiese nei dataset geografici (OSM)
3. Verifica incrociata con **Wikipedia** 
4. Attribuzione di uno **status attuale**: `Attiva`, `Sconsacrata`, `Demolita`, `NA`
5. Compilazione degli altri campi, consultabili nel seguente [README](../data/CSV/README.md)

## 5. Esempio di Ricerca

### Chiesa di S. Adriano

- **Nome dalla fonte**: "Chiesa di S. Adriano"
- **Risultati preliminari**: nessun risultato su Nominatim
- **Verifica**:
  - Identificata come ["Chiesa di Sant'Adriano al Foro"](https://it.wikipedia.org/wiki/Chiesa_di_Sant%27Adriano_al_Foro) tramite Wikipedia
  - Demolita nel tempo; situata originariamente nel Foro Romano
- **Decisione**:
  - Coordinate (`Lat` e `Long`) = `NA` (non più esistente in OSM)
  - `Status_Attuale` = `Demolita`
  - `Fonte_Verifica_Parallela` = `Wikipedia, Wikidata`

## 6. Risultati e Visualizzazioni

### 6.1 Analisi descrittiva del dataset

L’analisi è stata condotta principalmente tramite **LibreOffice Calc**, con possibili estensioni future su strumenti come **OpenRefine** per la pulizia e normalizzazione avanzata.

Su un totale di **60 chiese** registrate nella fonte di Diego Angeli, possiamo notare come:

- **47 chiese** risultano ancora **_attive_** come luoghi di culto
- **6 chiese** risultano **_demolite_**
- **2 chiese** risultano **_sconsacrate_**
- **5 chiese** hanno **_status non identificato_** (`Status_Attuale` = `NA`)

Informazioni secondarie:

- **12 chiese** presentano _coordinate non valide_ ovvero `NA` (ottenute via OSM/Nominatim)
- **13 chiese** non hanno altri nomi noti (`Altri_Nomi` : `NA`)
- **15 chiese** non hanno indicazioni di ubicazione nella fonte originale (`Indicazioni_Ubicazione_Fonte`)
- **4 chiese** non hanno il collegamento Wikidata: **non è stato trovato**.

> Questi risultati evidenziano l’incompletezza parziale del testo di Angeli e la difficoltà dell'identificazione per alcune chiese nel contesto attuale.

### 6.2 Analisi spaziale: distribuzione e vicinanza

- ### Nearest Neighbor Analysis (NNA)

La **Nearest Neighbor Analysis** è stata condotta con **QGIS** utilizzando il plugin "NN Analysis", su un subset di 48 chiese con coordinate valide [`DatasetAngeli_PuliziaCoordNA.csv`](../data/CSV/DatasetAngeli_PuliziaCoordNA.csv). 
Il file dei risultati testuali [`Risultati_NNA_Chiese.txt`](../qgis/analisi/Risultati_NNA_Chiese.txt) è disponibile nella cartella [`/qgis/analisi/`](../qgis/analisi/).

#### Risultati dell'analisi

| Parametro                                | Valore       | Descrizione                                                                   |
| ---------------------------------------- | ------------ | ----------------------------------------------------------------------------- |
| **Numero di punti**                      | 48           | Totale dei punti analizzati                                                   |
| **Distanza media osservata**             | 318.19 metri | Distanza media effettiva tra ciascun punto e il suo vicino più prossimo       |
| **Distanza media attesa**                | 352.70 metri | Distanza media attesa in caso di distribuzione completamente casuale          |
| **Indice del vicino più prossimo (NNI)** | 0.902        | Rapporto tra distanza osservata e attesa                                      |
| **Z-Score**                              | -1.30        | Statistica Z per valutare la significatività della deviazione dalla casualità |

#### Interpretazione

Il valore dell’indice NNI pari a **0.902** suggerisce una **leggera tendenza all’aggregazione spaziale**: le chiese sono mediamente più vicine tra loro di quanto ci si aspetterebbe in una distribuzione puramente casuale.

Tuttavia, il valore di **Z-Score = -1.30** non supera la soglia di significatività statistica (±1.96 per *p* < 0.05), il che implica che **la tendenza osservata non è statisticamente significativa**.

> In altre parole, la disposizione spaziale delle chiese **potrebbe essere il risultato del caso** e non suggerisce un pattern specifico con certezza.

#### Commento finale

L’analisi evidenzia una **distribuzione sostanzialmente casuale**, con una possibile (ma non confermata) aggregazione spaziale. 
Questo risultato è coerente con una diffusione urbana non rigidamente pianificata, e potrebbe riflettere la natura storica e stratificata del tessuto urbano romano.


- ### Distance Matrix

È stato generato un [**file CSV della matrice delle distanze**](../qgis/analisi/matrice_distanze_definitivo.csv) tra tutte le chiese con coordinate (metodo: distanza euclidea in metri, EPSG:3857), ma:
> **Non verrà analizzato all'interno di questo progetto**, pur restando disponibile per analisi future (es. clusterizzazione, itinerari, ecc.).


### 6.3 Visualizzazioni interattive

Le chiese con coordinate valide sono state mappate con:

- **QGIS**: per analisi spaziali, simbologie per status, e output statici e vettoriali 
- **Kepler.gl**: per visualizzazioni dinamiche 

Le visualizzazioni prodotte si trovano nelle cartelle [`/qgis/`](../qgis/) e [`/kepler/`](../kepler/) del progetto.


## 7. Preservazione e Condivisione

- I dati sono conservati su **GitHub**, con versionamento e documentazione
- Il dataset è stato caricato anche su [**Zenodo**](https://zenodo.org/records/15918009), per attribuzione DOI e conservazione a lungo termine 
- Backup locale su drive personale e pendrive
- I file sono organizzati per tipologia e processo (data, docs, kepler, qgis, tutorials)


## 8. Licenze e Riferimenti

### Licenze software utilizzati

| Strumento      | Licenza           |
|----------------|-------------------|
| QGIS           | GNU GPL v2        |
| Kepler.gl      | MIT               |
| OpenRefine     | BSD 3-Clause      |
| OpenStreetMap  | ODbL              |
| Wikipedia      | CC BY-SA 4.0      |

### Licenza del progetto

> Il progetto è distribuito con licenza [![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC_BY--SA_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)


## 9. Conclusioni

**SQMQ** è un progetto sperimentale che unisce ricerca storica e strumenti digitali per ricostruire, visualizzare e analizzare la distribuzione delle chiese di Roma. 
Grazie all’uso di dati aperti e formati interoperabili, il progetto può essere facilmente **esteso, replicato e integrato** con ulteriori fonti storiche, analisi sui dati testuali e ulteriori analisi statistiche e geospaziali.


[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.15918009.svg)](https://doi.org/10.5281/zenodo.15918009)


#### Nota finale
Per rendere più leggibile e accessibile la [pagina web del progetto](https://malemg.github.io/sqmq_project/), sono stati aggiunti due file nella cartella [`/docs`](../docs/) esclusivamente dedicati alla personalizzazione del tema grafico.

Questi file **non fanno parte del progetto di analisi geospaziale** in sé, ma servono unicamente a migliorarne la presentazione e l’accessibilità.

### File coinvolti

- `_config.yml`  
  ↳ Imposta il tema Jekyll `midnight` e abilita l’inclusione di stili personalizzati  
- `index.md`  
  ↳ Serve come punto di ingresso per la pagina web  
- `assets/css/style.scss`  
  ↳ Contiene le modifiche ai colori dei titoli per aumentare la leggibilità

### Obiettivi delle modifiche

- Applicare il tema visivo **Midnight**, ottimizzato per ambienti scuri
- **Aumentare il contrasto cromatico** dei titoli e sottotitoli
- Favorire una **visualizzazione accessibile** anche per utenti ipovedenti o daltonici

Tali modifiche **non influiscono sui dati, sul codice o sulla metodologia** del progetto **SQMQ**, ma solo sulla sua presentazione su GitHub Pages.


