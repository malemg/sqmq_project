# Visualizzazione Interattiva delle Chiese Romane — Kepler.gl

Questa cartella raccoglie i materiali relativi alla mappa interattiva delle chiese di Roma realizzata con **[Kepler.gl](https://kepler.gl/)**, uno strumento open source per l’esplorazione e la visualizzazione di dati geospaziali.

## Contenuto della cartella

- `VizChieseFiltered_KeplerGl.json`: configurazione esportata da Kepler.gl con layers, filtri e stili personalizzati.
- `VizChieseFiltered_KeplerGl.png`: immagine statica della visualizzazione esportata da Kepler.gl.

> **Nota:** Il file `.json` può essere ricaricato su Kepler.gl per replicare esattamente la visualizzazione.

## Dati utilizzati

Il dataset di partenza è:
- `data/csv/DatasetAngeli_PuliziaCoordNA.csv`

Contiene 48 chiese con coordinate pulite, ID e altri metadati.

## Obiettivi della visualizzazione

- Offrire una rappresentazione geospaziale esplorabile delle chiese romane.
- Visualizzare attributi come lo **status attuale** (_Attiva_, _Sconsacrata_, ecc.) attraverso simboli e colori.
- Fornire una base per ulteriori analisi o esplorazioni visuali.

## Come visualizzare la mappa

1. Vai su [Kepler.gl](https://kepler.gl/)
2. Clicca su **"Load Map"**
3. Carica il file `VizChieseFiltered_KeplerGl.json`
4. Interagisci con la mappa usando i layer, filtri e attributi già impostati

## Strumenti utilizzati

- [Kepler.gl](https://kepler.gl/)
- CSV (per il dataset)
- JSON (per la configurazione della mappa)

## Tutorial 

Se vuoi replicare il lavoro da zero partendo dal CSV, segui il [Tutorial a Kepler.gl](../tutorials/kepler_tutorial.md)



