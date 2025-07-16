# Cartella CSV - SIDE QUEST MAIN QUEST (SQMQ)

# Dataset Tabellari

### Indice
1. [Dataset Angeli Completo](#dataset-angeli-completo)
2. [Dataset Angeli Ripulito](#dataset-angeli-ripulito)

<a name="dataset-angeli-completo"></a>
## Dataset Angeli Completo

#### Nome del file 
[`DatasetAngeli_Completo.csv`](/data/CSV/DatasetAngeli_Completo.csv)

**Nota**:il file [`DatasetAngeli_Completo.csv`](/data/CSV/DatasetAngeli_Completo.csv) corrisponde alla versione v1.0 e rappresenta la base dati originale, utilizzata per tutte le fasi iniziali di analisi e validazione.

#### Descrizione 
Contiene l’elenco completo delle informazioni estratte dalla fonte Angeli, con una prima verifica incrociata tramite Wikipedia.
Include tutte le 60 chiese considerate nel progetto, inserite nell’ordine alfabetico originale della fonte.
È il file di riferimento per eventuali analisi testuali (ad es. tramite foglio di calcolo o OpenRefine) e per avere uno storico non filtrato.

#### Struttura 
* Numero righe: 60 (+1 intestazione)
* Numero colonne: 9 
    * __Intestazione Colonne__:
    * `ID_Chiesa` : numero progressivo per identificare ogni chiesa (da 001 a 060)
    * `Nome_Chiesa`: nome della chiesa come indicato nella fonte (_Angeli_)
    * `Altri_Nomi` : eventuali altre denominazioni riscontrate in OSM, Wikipedia o Wikidata
    * `Status_Attuale` : sono stati scelti quattro status possibili. __DEMOLITA__ (_la chiesa è stata demolita), __ATTIVA__ (_la chiesa è ancora attiva come luogo di culto) , __NA__ (nessuna informazione verificabile) , __SCONSACRATA__ (la chiesa è esistente, possibilmente visitabile, ma sconsacrata)
    * `Fonte_Verifica_Parallela`: fonte di confronto (wikipedia o wikidata) per verificare la colonna precedente
    * `Lat` : colonna che indica la coordinata geografica di _latitudine_ . L'intestazione per abbreviazione è stata onserita per essere riconosciuta facilmente dai sistemi Kepler.gl e QGIS. Il valore della coordinata è stato ricavato tramite OSM e Nominatem.
    * `Long` : colonna che indica la coordinata geografica di _longitudine_ . L'intestazione per abbreviazione è stata inserita per essere riconosciuta facilmente dai sistemi Kepler.gl e QGIS. Il valore della coordinata è stato ricavato tramite OSM e Nominatem.
   * `WIKIDATA` : identificativo univoco della eventuale chiesa (quando disponibile) 

<a name="dataset-angeli-ripulito"></a>
## Dataset Angeli Ripulito

#### Nome del file 
[`DatasetAngeli_PuliziaCoordNA.csv`](/data/CSV/DatasetAngeli_PuliziaCoordNA.csv)

**Nota**: il file [`DatasetAngeli_PuliziaCoordNA.csv`](/data/CSV/DatasetAngeli_PuliziaCoordNA.csv) corrisponde alla versione v1.0 e rappresenta il dataset pulito per l’uso diretto in Kepler.gl e QGIS.

#### Descrizione 

Rispetto al dataset completo, questo file esclude tutte le chiese con coordinate non disponibili (NA), in modo da garantire una corretta visualizzazione e affidabilità nell’analisi spaziale.
È la versione operativa del dataset, utilizzata per generare mappe e calcolare distanze spaziali senza introdurre errori dovuti a valori mancanti.

#### Struttura 
* Numero righe: 48 (+1 intestazione)
* Numero colonne: 9 
    * __Intestazione Colonne__:
    * `ID_Chiesa` : numero progressivo per identificare ogni chiesa (da 001 a 060)
    * `Nome_Chiesa`: nome della chiesa come indicato nella fonte (_Angeli_)
    * `Altri_Nomi` : eventuali altre denominazioni riscontrate in OSM, Wikipedia o Wikidata
    * `Status_Attuale` : sono stati scelti quattro status possibili. __DEMOLITA__ (_la chiesa è stata demolita), __ATTIVA__ (_la chiesa è ancora attiva come luogo di culto) , __NA__ (nessuna informazione verificabile) , __SCONSACRATA__ (la chiesa è esistente, possibilmente visitabile, ma sconsacrata)
    * `Fonte_Verifica_Parallela`: fonte di confronto (wikipedia o wikidata) per verificare la colonna precedente
    * `Lat` : colonna che indica la coordinata geografica di _latitudine_ . L'intestazione per abbreviazione è stata onserita per essere riconosciuta facilmente dai sistemi Kepler.gl e QGIS. Il valore della coordinata è stato ricavato tramite OSM e Nominatem.
    * `Long` : colonna che indica la coordinata geografica di _longitudine_ . L'intestazione per abbreviazione è stata inserita per essere riconosciuta facilmente dai sistemi Kepler.gl e QGIS. Il valore della coordinata è stato ricavato tramite OSM e Nominatem.
   * `WIKIDATA` : identificativo univoco della eventuale chiesa (quando disponibile) 

#### Copia con versionamento esplicito:

- [`DatasetAngeli_Completo_v1.0.csv`](/data/CSV/DatasetAngeli_Completo_v1.0.csv)
- [`DatasetAngeli_PuliziaCoordNA_v1.0.csv`](/data/CSV/DatasetAngeli_PuliziaCoordNA_v1.0.csv)

Questi file sono **identici ai corrispettivi principali**, ma includono nel nome la versione (`v1.0`) per assicurare:

- una **migliore tracciabilità nel tempo**
- la **riproducibilità delle analisi** 
- la **possibilità di estendere o aggiornare il lavoro** mantenendo coerenza con questa prima versione stabile

Questa scelta è in linea con i **principi FAIR**, in particolare con:

- **Findability** (trovabilità della versione usata) 
- **Accessibility** (chiarezza nell’accesso ai dati) 
- **Interoperability** (compatibilità con altri strumenti e sistemi) 
- **Reusability** (riutilizzo garantito e documentato) 

