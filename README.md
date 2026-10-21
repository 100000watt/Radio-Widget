# Radio Widget

Un piccolo player per ascoltare le radio online su Windows, senza tenere aperto il browser.
Una finestrella elegante, sempre in primo piano se vuoi, che vive anche nella system tray.

Le stazioni arrivano da [radio-browser.info](https://www.radio-browser.info/), un database
libero e gratuito con decine di migliaia di radio di tutto il mondo.

## Funzioni

- **Cerca** tra le radio per nome e filtra per paese (Italia, UK, USA, Francia, Germania, Spagna o tutti).
- **Preferite**: salva le tue radio e ritrovale nel tab dedicato.
- **Info sul brano**: una riga scorrevole mostra «Artista – Titolo» quando la radio lo comunica.
- **6 temi** (Notte viola, Oceano, Smeraldo, Tramonto, Grafite, Chiaro) e **opacità regolabile** dal 100% al 70%.
- **Sempre in primo piano** attivabile e disattivabile.
- **System tray**: riduci il widget accanto all'orologio e la musica continua.
- **Avvio con Windows** attivabile dal menu.
- **Una sola istanza**: riaprirlo porta avanti quello già in esecuzione.
- **Ricorda tutto**: tema, opacità, posizione, volume, ultima radio, preferite, tab e paese scelti.

## Come si usa

| Azione | Come |
|---|---|
| Ascoltare una radio | Clic sulla radio nella lista |
| Fermare / riavviare | Pulsante ▶ / ■ nel player (o dal menu della tray) |
| Cercare | Tab **Esplora**, scrivi il nome e scegli il paese |
| Aggiungere alle preferite | ☆ nel player, oppure tasto destro sulla radio |
| Spostare il widget | Trascina la barra in alto (dove c'è «RADIO») |
| Ridurre nella tray | Pulsante **—**; clic sull'icona nella tray per riaprirlo |
| Chiudere del tutto | Pulsante **✕**, oppure **Esci** dal menu |

### Menu col tasto destro

Un clic destro in un punto qualsiasi del widget apre il menu:

- **Tema**: cambia i colori.
- **Opacità**: da 100% a 70%, a passi di 5.
- **Sempre in primo piano**: attiva/disattiva.
- **Avvia con Windows**: il widget parte da solo all'accesso.
- **Copia info grezze brano (diagnostica)**: copia negli appunti i metadati ricevuti dalla radio (utile se il titolo appare strano).
- **Riduci nella tray** ed **Esci**.

## Installazione

### Opzione 1 – Installer (consigliata)

Esegui `RadioWidget-Setup-<versione>.exe`. La procedura guidata è in italiano o inglese,
non richiede permessi di amministratore e permette di scegliere se avviare il programma con Windows
e se creare l'icona sul desktop.

Alla prima apertura Windows SmartScreen può mostrare un avviso perché l'installer non è firmato:
clicca **Ulteriori informazioni** e poi **Esegui comunque**.

## Dove vengono salvati i dati

`%APPDATA%\RadioWidget\data.json`: preferite, tema, opacità, posizione, volume, ultima radio.
Se disinstalli il programma ti viene chiesto se eliminare anche questi dati.

## Come funziona (e privacy)

- La lista delle radio viene richiesta all'API pubblica di radio-browser.info.
- L'audio è riprodotto direttamente dallo stream della radio, tramite Qt Multimedia.
- Per mostrare il titolo del brano, ogni 15 secondi il widget apre per un istante una seconda
  connessione allo stesso stream e legge i metadati ICY (il sistema usato da Shoutcast/Icecast).
  Il titolo viene ripulito dai campi tecnici che alcune radio accodano (codici, UUID, `chiave="valore"`).
- Nessun dato personale viene inviato o raccolto.

## Problemi comuni

**«Stream non disponibile».** Alcune stazioni usano formati o indirizzi non gestiti o non più attivi.
Prova un'altra radio, o cerca la stessa radio con un nome simile: spesso ci sono più flussi.

**Non compare il titolo del brano.** Non tutte le radio lo trasmettono (in particolare quelle in streaming HLS).
In quel caso la riga mostra solo lo stato.

**Il titolo contiene una stringa strana.** Tasto destro → *Copia info grezze brano (diagnostica)* e
incolla il testo dove segnali il problema: mostra esattamente cosa invia la radio.




