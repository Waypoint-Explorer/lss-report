---
layout: default
title: Architettura di Dettaglio
parent: Design Architetturale
nav_order: 2
---

# Architettura di Dettaglio
Per avere una visione della struttura generale del sistema, è stato creato un diagramma delle classi (Figura \ref{fig:class-diagram}). Esso modella la suddivisione del sistema negli elementi precedentemente individuati, cercando inoltre di rappresentare le relazioni presenti tra i vari componenti.

<div align="center">
<img src="../../img/diagramma-classi.png" alt="Diagramma delle classi" >
<p align="center" id="fig99">[Fig ] Diagramma delle classi</p>
</div>

Per quanto riguarda il sistema in dettaglio, è stata adottata una suddivisione in due elementi principali, che verranno successivamente approfonditi: la web app (detta anche explorer app) e il dispositivo (chiamato anche device). Considerando che il sistema è destinato all'uso all'aperto da parte di cittadini e turisti, l'interazione dell'utilizzatore con funzionalità come la mappa dei percorsi e la scansione dei codici QR avverrà principalmente attraverso smartphone. Inoltre, è necessario che un dipendente del Comune possa utilizzarlo tramite un computer da ufficio. Per queste ragioni, è stata scelta l'implementazione di un'applicazione web unica, piuttosto che un'app mobile.

## Web app
A seguito dell'analisi dei requisiti, capite le esigenze del possibile committente, sono state ideate due architetture del sistema da utilizzare rispettivamente durante la fase di sviluppo interno e durante il deploy del sistema.
Entrambe le architetture dividono la web application in tre macro componenti che sono:
- frontend: responsabile della parte grafica dell'applicazione, permette il rendering dell'interfaccia utente e l'interazione con il sistema da parte degli utenti finali;
- backend: attraverso la sua architettura REST API permette di ottenere e/o inserire dati nel sistema;
- database: rende possibile il mantenimento dei dati del sistema e fornisce metodi per l'accesso ottimizzato ad essi.

Ciascuno di questi tre componenti risiede all'interno di un container \textit{Docker}\cite{docker} dedicato al fine di rendere il sistema modulare e facilmente installabile dato che, grazie alle configurazioni presenti per ciascuno di essi e al tool \textit{Docker Compose}\cite{dockerCompose}, è possibile avviare l'intero sistema attraverso un unico comando e senza la necessità di dover installare o configurare librerie esterne necessarie durante l'esecuzione.
Come già accennato, la prima delle due architetture ideate è pensata per lo sviluppo agevole del sistema e, in Figura \ref{fig:local architecture}, si può osservare uno schema riassuntivo di essa.

<div align="center">
<img src="../../img/architecture.png" alt="Architettura del sistema durante lo sviluppo" >
<p align="center" id="fig99">[Fig ] Architettura del sistema durante lo sviluppo</p>
</div>

Il sistema così realizzato è pensato per essere eseguito in locale sulla macchina dello sviluppatore mantenendo al tempo stesso i benefici di modularità e configurazione automatica dell'ambiente di esecuzione.
Questa architettura è utile per poter permettere ad ogni sviluppatore di avere una copia del sistema intero per poter sviluppare in modo indipendente dagli altri le proprie parti implementative. Essa, ovviamente, non permette l'utilizzo da parte degli utenti finali, per questo motivo, la seconda architettura mostrata in Figura \ref{fig:remote architecture}, è stata realizzata principalmente per permettere l'effettivo utilizzo del sistema una volta completato.

<div align="center">
<img src="../../img/architecture_remote.png" alt="Architettura del sistema completato" >
<p align="center" id="fig98">[Fig ] Architettura del sistema completato</p>
</div>

Questa seconda architettura è pensata per essere impiegata utilizzando un server remoto dove, oltre al sistema sviluppato, è presente anche un reverse proxy server realizzato utilizzando \textit{NGINX}\cite{nginx}. Una volta configurato, il reverse proxy server permette a client esterni di interagire con le istanze dei container docker presenti nel server e che ospitano, in maniera simile a prima, i macro componenti del sistema.

Dal momento che la maggior parte delle informazioni dell'applicazione saranno visionabili mediante una mappa, grafici statistici o in formato testuale, si è deciso di porsi come problema e obiettivo quello di rendere accessibile l'interfaccia dell'applicazione, con particolare attenzione alle persone daltoniche e dislessiche.\
Il design dell'interfaccia utente è stato eseguito considerando che la maggior parte degli utilizzatori dell'applicazione vi accederanno tramite smartphone, come già accennato in precedenza, per cui è stato seguito un approccio *mobile-first*. \
Inoltre, si è seguito uno stile minimale nella progettazione delle schermate, con lo scopo di rendere più facilmente comprensibile all'utilizzatore il ruolo di ciascun componente nell'applicazione. Per lo stesso motivo, sono stati adottati o progettati i componenti grafici cercando di seguire alcuni standard de facto sul web, in modo che l'utente possa facilmente acquisire una certa familiarità con l'applicazione.

## Dispositivo
Analizzando i requisiti son state dedotte diverse informazioni che hanno permesso di passare alla fase di progettazione del dispositivo. Per prima cosa, anche per motivi di costi, il dispositivo deve essere molto semplice e avere il minimo numero di componenti. <br>
Esso deve avere la possibilità di essere posizionato lontano da centri abitati e funzionare anche se scollegato da alimentazione e dalla connessione internet. Deve essere quindi il più possibile autonomo. Per fare ciò è necessario che abbia una alimentazione a batteria con l'eventuale ricarica tramite pannello fotovoltaico. <br>
Deve riconoscere i guasti non gravi in modo da notificarlo agli amministratori.
Inoltre, il sistema deve essere ottimizzato allo scopo di risparmiare energia e comunque avere tempi di risposta brevi.

Il dispositivo ha due funzioni principali:
- raccogliere periodicamente dati ambientali;
- generare un codice QR a richiesta.

Per raccogliere periodicamente i dati ambientali deve innanzitutto potere ottenere data e ora senza l'utilizzo di internet. Dato che il dispositivo è pensato per rimanere all'esterno, si è pensato di utilizzare il GPS. Questo infatti, oltre a fornire le coordinate geografiche, fornisce anche data e ora. In questo modo, il dispositivo rimane sempre aggiornato e non è necessario impostare alcun dato manualmente.
Per rilevare i dati ambientali è invece necessario l'utilizzo di un sensore che converta da valori fisici a valori digitali. <br>
Essendo appunto scollegato da internet, l'unica maniera che il dispositivo ha di inviare i dati raccolti è tramite lo smartphone dell'utente. Attraverso la scansione del codice QR quindi, deve essere possibile ottenere sia un codice univoco che permette la verifica del fatto che l'utente sia effettivamente passato da quel dispositivo, sia i dati ambientali raccolti fino a quel momento. Per possedere tutte queste informazioni il codice QR deve contenere una stringa di cifre, come mostrato nell'immagine sottostante.

<div align="center">
<img src="../../img/device-qr-data-packet.jpg" alt="Stringa dati del QR code" >
<p align="center" id="qr-data">[Fig ] Stringa dati del QR code</p>
</div>

Nel dettaglio, il pacchetto è composto da:
- ID - sequenza di 16 cifre univoca;
- ID dinamico - sequenza di 32 cifre univoca che cambia ogni volta che viene generato un codice QR;
- Errori - sequenza di 6 cifre, ognuna rappresenta un errore;
- Prima timestamp - sequenza di 10 cifre, per la prima timestamp catturata dal dispositivo;
- Dati - sequenza di cifre la cui lunghezza equivale al numero dei dati raccolti dal dispositivo, ogni dato è composto da:
        
    - Numero di ore dalla prima timestamp - sequenza composta da 3 cifre;
    - Temperatura - sequenza composta da 3 cifre, dove la prima indica il segno;
    - Pressione - sequenza di 5 cifre;
    - Umidità - sequenza di 2 cifre;
    - Qualità dell'aria - sequenza di 2 cifre.

Una volta definito ciò che è necessario per il dispositivo, è stato realizzato il seguente diagramma a blocchi che rappresenta l'architettura generale del sistema.

<div align="center">
<img src="../../img/device-block-diagram.jpg" alt="Architettura del dispositivo" >
<p align="center" id="device-block">[Fig ] Architettura del dispositivo</p>
</div>

Come si può vedere dal diagramma, il dispositivo è composto da diversi elementi: 

- l'ESP32, il core del dispositivo che gestisce tutti gli altri componenti;
- lo schermo per mostrare i dati all'utente, comunica tramite interfaccia SPI;
- il modulo GPS per ottenere la posizione e il tempo attuale, comunica tramite interfaccia UART;
- il sensore per ottenere dati ambientali, comunica tramite interfaccia I2C;
- il pulsante di reset per cancellare tutto quello che è stato salvato;
- il pulsante per aggiornare il codice QR e stampare a schermo;
- la batteria che fornisce alimentazione al dispositivo;
- il pannello fotovoltaico per ricaricare la batteria.

Questa architettura rispecchia sia la parte firmware che la parte hardware, infatti ognuno di questi componenti e la loro interazione è fondamentale per il corretto funzionamento del sistema. <br>
Inoltre è stato realizzato uno schema hardware per definire meglio come i vari componenti sono collegati tra di loro.

<div align="center">
<img src="../../img/device-scheme.png" alt="Schema collegamenti del dispositivo" >
<p align="center" id="device-scheme">[Fig ] Schema collegamenti del dispositivo</p>
</div>

Nell'immagine sotto riportata viene mostrato un modello 3D di come potrebbe essere realizzato il dispositivo fisico.
Simile ad una casetta per uccelli, che come tetto ha dei pannelli fotovoltaici e di fronte mostra il display ed il pulsante per ottenere il codice QR da scansionare. Inoltre presenta dei fori laterali per il ricircolo dell'aria.

<div align="center">
<img src="../../img/device-prototype.png" alt="Modello 3D di un possibile dispositivo" >
<p align="center" id="device-prototype">[Fig ] Modello 3D di un possibile dispositivo</p>
</div>

