# Cartella QGIS - SIDE QUEST MAIN QUEST (SQMQ)

Questa cartella contiene tutto il materiale relativo all’elaborazione GIS del progetto **SIDE QUEST - MAIN QUEST (SQMQ)**, realizzato con **QGIS** .

## Contenuto 

- [`progetto_SQMQ.qgz`](/qgis/progetto_SQMQ.qgz) 
  File del progetto QGIS che contiene i layer caricati e la configurazione delle analisi spaziali (proiezioni, style, layer). 

- [`/analisi/`](/qgis/analisi) 
  Cartella con i risultati delle analisi spaziali:
  - [`matrice_distanze_definitivo.csv`](/qgis/analisi/matrice_distanze_definitivo.csv): matrice delle distanze tra le chiese
  - [`Risultati_NNA_Chiese.txt`](/qgis/analisi/Risultati_NNA_Chiese.txt): output del test di Nearest Neighbour Analysis (NNA)
  

## Descrizione del progetto QGIS

Il progetto si basa su un dataset di **48 chiese** (su 60 iniziali - sono state escluse le chiese senza coordinate) geolocalizzate nella zona di Roma. I dati sono forniti in coordinate geografiche (EPSG:4326) e rielaborate/proiettate in sistema metrico (EPSG:32633) per l'analisi spaziale. 
Le analisi spaziali effettuate includono:

- **Distance Matrix**:calcolo delle distanze in metri tra ogni coppia di chiese
- **Nearest Neighbour Analysis (NNA)**: test per valutare se la distribuzione spaziale dei punti è clusterizzata, casuale o uniforme

## Come utilizzare questa cartella

1. Apri il file [`progetto_SQMQ.qgz`](/qgis/progetto_SQMQ.qgz)  in **QGIS 3.44** (o superiore).
2. Assicurati che il file [`DatasetAngeli_PuliziaCoordNA.csv`](../data/CSV/DatasetAngeli_PuliziaCoordNA.csv) sia disponibile nel percorso corretto ([`/data/CSV/`](../data/CSV) della repo).
3. Esplora i layer, le analisi e la visualizzazione integrata nel progetto.
4. Consulta la cartella [`qgis/analisi/`](/qgis/analisi) per accedere ai risultati testuali o tabellari delle analisi.
5. Per interpretazioni e contesto metodologico, fai riferimento al [`README.md`](../docs/README.md) principale della repo.

## Note tecniche

- **CRS originale (input)**: EPSG:4326 – WGS 84 (coordinate geografiche in gradi decimali)
- **CRS per analisi metriche**: EPSG:32633 – WGS 84 / UTM Zone 33N
- Il progetto è stato sviluppato su **Linux Mint** utilizzando **QGIS 3.44 “Solothurn”**

### Tutorial 

Se vuoi realizzare il lavoro da zero partendo dal CSV, segui il [Tutorial a QGIS](../tutorials/qgis_tutorial.md)





