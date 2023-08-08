---
layout: default
title: Test
has_children: false
nav_order: 8
---

# Test e Performance
## Web App
La valutazione delle performance della web app riguarda principalmente aspetti legati all'utilizzo da parte degli utenti come usabilità, reattività agli input degli utenti e velocità nei tempi di risposta.

Per quanto riguarda i tempi di risposta del sistema durante l'utilizzo dell'applicazione, è stato utilizzato l'apposito tool di valutazione fornito con i moderni browser basati su *Chromium* tra i quali rientrano quelli in cui si garantisce la compatibilità con questo progetto. Attraverso questi strumenti è possibile configurare e simulare un dispositivo qualunque analizzando nel dettaglio i risultati.\
E' stato scelto di concentrarsi principalmente su un dispositivo mobile dotato di una connessione ad internet di tipo *4G LTE*, ovvero una delle connessioni più diffuse attualmente.
Anche se una rete di tipo *4G LTE* offre teoricamente velocità di picco di 150Mbps per il download e 50Mbps per l'upload <a href="#1">[1]</a>, è stato scelto di limitare ulteriormente la connessione a 20Mbps per il download e 5Mbps per l'upload, che corrispondono a velocità che si avvicinano maggiormente a quelle riscontrabili nell'utilizzo reale di queste reti <a href="#2">[2]</a>.

Di seguito è inserita una tabella che riporta i tempi di caricamento di alcune delle funzioni ritenute più importanti del sito.
Come si può notare, l'utilizzo di *Vue*, basato sul concetto di single page application, richiede un notevole tempo di caricamento iniziale, comunque inferiore ai 3 secondi. Dopodiché, l'utilizzo diventa più consistente e veloce, richiedendo un tempo di caricamento prossimo al secondo solamente nello svolgimento delle operazioni più impegnative. Come già detto nei requisiti non funzionali, l'obbiettivo era di seguire i suggerimenti indicati in un articolo del *Nielsen e Norman Group* <a href="#3">[3]</a>, secondo cui è estremamente importante dare una buona impressione ad un utente entro i 10 secondi per mantenere la sua attenzione. Ovviamente un tempo di riposta prossimo o superiore a questo valore è sicuramente non adeguato ad un utilizzo efficiente e gradevole dell'applicazione. Sempre nella tabella si può notare di come, senza utilizzare le funzionalità di caching offerte da *Vue*, i tempi di riposta diventano molto meno consistenti.

Per quanto riguarda l'occupazione di memoria dell'applicazione, si ha un uso di memoria dinamica allocata da *JavaScript* per l'esecuzione di circa 6,9MB con un massimo di 30,9MB. La quantità di dati caricati tramite la rete internet a seguito del primo caricamento corrisponde invece a circa 5,3MB.

|**Operazioni svolte**|**normale (s)**|**senza cache (s)**|
|---------------------|---------------|-------------------|
| Caricamento iniziale homepage | 2,78 | 0,11 |
| Caricamento mappa utente | 0,65 | 0,89 |
| Caricamento mappa amministratore con misure | 1,29 | 3,65 |
| Caricamento menu gestione | 0,25 | 0,26 |
| Caricamento storico utente | 0,18 | 0,37 |
| Login | 0,67 | 0,48 |

Per quanto riguarda l'accessibilità della web app, sono stati effettuati test per garantire che fossero soddisfatte le WCAG (Web Content Accessibility Guidelines). In particolare, per la verifica di tutte le scelte dei colori all'interno del sito nei vari componenti e il colore del testo sovrastante, è stato utilizzato *WebAIM* <a href="#4">[4]</a>. La seguente tabella riporta alcune delle valutazioni eseguite attraverso questo tool:

|**Oggetto**|**contrast ratio**|**compliance**|
|-----------|------------------|--------------|
| Testi | 12,63 : 1 | WCAG AAA |
| Testo secondario | 11,24 : 1 | WCAG AAA |
| Pulsanti | 11,24 : 1 | WCAG AAA |
| Elementi selezionati | 11,28 : 1 | WCAG AAA |

Per tutti gli elementi principali del sito, come ad esempio i testi e gli elementi grafici principali, si ottiene un rapporto del contrasto superiore a 7:1 soddisfacendo i requisiti imposti dallo standard scelto.

## Device
Per quanto riguarda il dispositivo fisico, gli aspetti da prendere in considerazione per valutare le performance sono i seguenti:
- **Consumo di energia**: il dispositivo, essendo alimentato solo tramite batteria, deve ridurre al minimo i consumi. Attraverso l'uso di un multimetro è stato possibile rilevarli ogni volta che si verifica l'esecuzione di una determinata operazione.\
Il numero di esecuzioni al giorno sono considerate al minimo, in quanto per il GPS dipende se riesce ad ottenere il segnale, altrimenti ritenta l'ora successiva. \
Invece per lo schermo il numero di esecuzioni dipende, oltre all'aggiornamento quando vengono rilevati nuovi dati ambientali, anche da quante persone premono il pulsante per ottenere il codice QR. \
Per il resto del tempo il dispositivo rimane in *Deep Sleep* consumando all'incirca 0.4mA.

|**Esecuzione**|**tempo medio (s)**|**consumo (mA)**|**n esec. al giorno**|
|--------------|-------------------|----------------|---------------------|
| Ottenimento GPS | 40 | 60 | minimo 4 |
| Aggiornamento schermo | 4 | 100 | minimo 24 |
| Calibrazione del sensore | 25 | 50 | 24 |

- **Precisione timer interno**: l'ESP32 possiede un timer interno che gli permette di mantenere la data e l'ora. Purtroppo però è stato calcolato, confrontando con orologi più precisi, che ogni ora perde circa 15 secondi. Per questo è necessario aggiornare data e ora più volte nell'arco di una giornata. 
- **Precisione dati ambientali**: il sensore BME680 è molto versatile e anche abbastanza preciso. Confrontando i valori rilevati con quelli di altri dispositivi è stato constatato che la misura di temperatura è molto precisa e rispetta l'errore di ±1.0°C. L'umidità invece ha un errore che è maggiore di quanto dichiarato (±3\%) in quanto si discosta dal +5\% al +7\%. Gli altri valori non sono stati controllati, non avendo a disposizione dispositivi che le rilevassero.
- **Tempo di risposta**: questo dato interessa maggiormente gli utenti che andranno ad utilizzare il dispositivo. Il tempo che trascorre tra la pressione del pulsante e la stampa a schermo del codice QR è di circa 4.5 secondi, purtroppo questo valore è dato dalla tipologia di display. Essendo un *Electronic Paper* ha un tempo di refresh maggiore rispetto agli altri schermi più comuni. Infatti nelle caratteristiche è dichiarato che il tempo di refresh è di almeno 4 secondi.

## Riferimenti

<a id="1">[1]</a> Pagina Wikipedia 4G, https://en.wikipedia.org/wiki/4G

<a id="2">[2]</a> 4G.co.uk, https://www.4g.co.uk/how-fast-is-4g/

<a id="3">[3]</a> Nielsen Norman Group, *How Long Do Users Stay on Web Pages?*, https://www.nngroup.com/articles/how-long-do-users-stay-on-web-pages/

<a id="4">[4]</a> WebAIM, https://webaim.org/resources/contrastchecker/