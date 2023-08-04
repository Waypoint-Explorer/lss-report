---
layout: default
title: Architettura di Dettaglio
parent: Design Architetturale
nav_order: 2
---

# Architettura di Dettaglio
Per l'architettura generale del sistema, è stata adottata una suddivisione in due elementi principali: la web app (detta anche explorer app) e il dispositivo (chiamato anche device). Questi elementi saranno successivamente spiegati in dettaglio. Considerando che il sistema è destinato all'uso all'aperto da parte di cittadini e turisti, l'interazione dell'utente con funzionalità come la mappa dei percorsi e la scansione dei codici QR avverrà principalmente attraverso smartphone. Inoltre, è necessario che un dipendente del Comune possa utilizzarlo tramite un computer da ufficio. Per queste ragioni, è stata scelta l'implementazione di un'applicazione web unica, piuttosto che un'app mobile.

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