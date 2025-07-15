# Cartella Analisi - QGIS

Questa cartella contiene i risultati delle analisi spaziali effettuate sul dataset delle chiese.

## File presenti

- **matrice_distanze_definitivo.csv**
  Matrice delle distanze in metri tra ogni coppia di chiese, calcolata tramite lo strumento "Distance Matrix" di QGIS con dati proiettati in EPSG:32633. 
  _Il file può essere ulteriormente analizzato con software come Python (pandas, geopandas) o R (sf, sp), anche se in questo progetto non verrà approfondito._

- **Risultati_NNA_Chiese.txt** 
  Risultati del Nearest Neighbour Analysis (NNA), che valuta la distribuzione spaziale delle chiese (clusterizzata, casuale o regolare). 

## Note

- Entrambi i file sono prodotti a partire dal layer proiettato nel sistema EPSG:32633 (coordinate metriche, metri). 
- I risultati offrono un primo approfondimento sulla distribuzione e la vicinanza spaziale delle chiese nel dataset.
