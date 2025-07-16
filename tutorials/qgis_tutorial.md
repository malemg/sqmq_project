# QGIS Tutorial: Analisi spaziale delle chiese con QGIS

Questa guida spiega come caricare i dati geografici delle chiese romane, reimpostare correttamente il sistema di riferimento, ed eseguire analisi spaziali in **QGIS** (Nearest Neighbour Analysis e Distance Matrix).


### Dati

- **Dati**: il file [`DatasetAngeli_PuliziaCoordNA.csv`](../data/CSV/DatasetAngeli_PuliziaCoordNA.csv)


## Crea un nuovo progetto e imposta il il sistema di riferimento (CRS)

- Vai su `File → Nuovo progetto`
- In basso a destra, clicca sul codice CRS attuale (es. `EPSG:4326`)
- Cerca e seleziona: `EPSG:32633 – WGS 84 / UTM zone 33N` (metri)
- Clicca su **OK**


## Carica il file CSV con i punti delle chiese

- Vai su: `Layer → Aggiungi Layer → Aggiungi layer di testo delimitato`
- Seleziona: `DatasetAngeli_PuliziaCoordNA.csv`

### Parametri da impostare:

| Campo         | Valore                          |
|---------------|----------------------------------|
| **X field**   | `long` (longitudine)            |
| **Y field**   | `lat` (latitudine)              |
| **CRS**       | `EPSG:4326 – WGS 84`            |

- Clicca su **Aggiungi**

I punti verranno visualizzati correttamente grazie alla trasformazione automatica tra CRS.


## Salva il layer con proiezione metrica

Per eseguire analisi spaziali, salva il layer nel sistema `EPSG:32633`:

- Clic destro sul layer → `Esporta → Salva con nome`
- Imposta:
  - **Formato**: GeoPackage (`.gpkg`) o Shapefile (`.shp`)
  - **CRS**: `EPSG:32633 – WGS 84 / UTM zone 33N`
  - **Nome file**: `chiese_proiettato.gpkg`
  - Salva nella cartella `qgis/`

Il layer è ora pronto per analisi metriche come NNA e matrici di distanza.


## Nearest Neighbour Analysis (NNA)

- Vai su `Processing → Toolbox → Nearest Neighbour Analysis`
- **Input layer**: `chiese_proiettato.gpkg`
- Esegui l’analisi

### Nota:
L'NNA **non viene salvata** nel file `.qgz`! 
Salva i risultati manualmente come `.txt`, come ad esempio: [`Risultati_NNA_Chiese.txt`](../qgis/analisi/Risultati_NNA_Chiese.txt)


## Calcola la Distance Matrix

- Vai su `Processing → Toolbox → Distance Matrix`
- Parametri consigliati: 

| Campo                     | Selezione                            |
|--------------------------|---------------------------------------|
| **Input point layer**    | `chiese_proiettato`                   |
| **Target point layer**   | `chiese_proiettato`                   |
| **Unique ID field**      | `Nome_Chiesa`                  |
| **Output matrix type**   | `Linear (N * k lines)`                |
| **Number of nearest k**  | `0` (per tutte le coppie)             |
| **Output**               | `analisi/matrice_distanze.csv`        |

- Dopo l'elaborazione, esporta il risultato se necessario:
  - Clic destro sul layer tabellare → `Esporta → Salva con nome`
  - Formato: `CSV`
  - CRS: lascia invariato

Ora la matrice è salvata e può essere usata per ulteriori analisi (es. in Python o R).

## File correlati nella repository

- [`qgis/progetto_SQMQ.qgz`](../qgis/progetto_SQMQ.qgz) → progetto completo
- [`qgis/analisi/risultati_nna_chiese.txt`](../qgis/analisi/risultati_nna_chiese.txt) → output dell'NNA
- [`qgis/analisi/matrice_distanze.csv`](../qgis/analisi/matrice_distanze.csv) → matrice delle distanze tra le chiese

## Requisiti

- **Software**: [QGIS](https://qgis.org/) versione 3.x (consigliata: 3.44 Solothurn)
- **Coordinate**: ottenute con Nominatim → in gradi decimali, CRS = EPSG:4326



### Extra

> Puoi usare la matrice CSV per analisi successive in Python, R o fogli di calcolo



