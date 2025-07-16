# Kepler Tutorial: Visualizzazione delle chiese romane con Kepler.gl

Questa guida spiega come riprodurre la mappa interattiva delle chiese romane a partire dal file CSV presente nella cartella `data/`.

Utilizzeremo **[Kepler.gl](https://kepler.gl/)**, una potente piattaforma open-source per la visualizzazione e l'analisi di dati geospaziali, direttamente dal browser.

## Dati 
- Il file dati da utilizzare è: [`DatasetAngeli_PuliziaCoordNA.csv`](../data/CSV/DatasetAngeli_PuliziaCoordNA.csv)-> Contiene 48 chiese di Roma, con coordinate in formato EPSG:4326

### Come ricreare la mappa

1. **Carica il dataset**
* Vai su [Kepler.gl](https://kepler.gl/)
* Clicca su **"Add Data"** e seleziona/trascina il file [`DatasetAngeli_PuliziaCoordNA.csv`](../data/CSV/DatasetAngeli_PuliziaCoordNA.csv)

2. **Imposta filtri e colori** 
* Vai su **Layers** 
* Scorri sulla sezione **Fill Color**:
- in **Color Based On** seleziona `Satus_Attuale`
- in **Color Scale** la modalità `Custom Ordinal`
- Personalizza i colori assegnati a:
- `Attiva`
- `Sconsacrata`
- `NA`

**Nota**: _le chiese con `Status_Attuale` `Demolita` non sono presenti nel dataset filtrato e quindi non compariranno nella mappa.

3. **Attivare le etichette**
Sempre nel pannello **Layers**:
- Attiva la sezione **Label**
  - In **Label By**, seleziona `ID_Chiesa`
  - Le chiese saranno visibili con il loro identificativo numerico sulla mappa

## Suggerimenti

- Puoi salvare la visualizzazione in formato `.json` per riutilizzarla in futuro
- Per uno snapshot statico, usa il tasto **Export Image**

## File correlati nella repository

- [`kepler/VizChieseFiltered_KeplerGl.json`](../kepler/VizChieseFiltered_KeplerGl.json) → configurazione salvata della mappa
- [`kepler/VizChieseFiltered_KeplerGl.png`](../kepler/VizChieseFiltered_KeplerGl.png) → screenshot statico

## Requisiti

- Browser aggiornato (consigliato: Firefox, Chrome)
- Connessione Internet attiva

