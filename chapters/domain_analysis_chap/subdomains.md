---
layout: default
title: Sottodomini
parent: Analisi del Dominio
nav_order: 2
---

# Sottodomini
I sottodomini hanno il ruolo di suddivisione e organizzare le varie parti che compongono il progetto. Essi rappresentano aree specifiche di funzionalità, ognuna con il proprio scopo e compito distintivo per permettere un miglioramento nell'efficienza durante lo sviluppo e la manutenzione. In particolare, sono stati individuati i seguenti sottodomini che compongono il nostro progetto e che contribuiscono alla realizzazione delle parti fondamentali del sistema complessivo:
- percorsi: si occupa della creazione dei percorsi, aggiunta di tappe ad un percorso, creazione delle tappe, aggiunta di un marcatore ad una tappa, esecuzione di un percorso;
- marcatori: si occupa dell'inserimento nel sistema dei marcatori e della loro gestione nel mondo fisico nelle operazioni di rilevazione tramite sensori e controllo del funzionamento corretto del dispositivo;
- coupon: si occupa dell'aggiunta di nuovi coupon e del riscatto dei coupon da parte degli esploratori;
- utenti: si occupa della registrazione di un nuovo utente esploratore, gestione dello storico degli utenti esploratori, accesso degli utenti esploratori e amministratori;
- dati ambientali: gestisce i dati ambientali riguardanti un'area geografica, includendo l'aggiunta nel sistema e le attività di analisi dei dati.

<div align="center">
<img src="../../img/core-domain-chart.svg" alt="Core Domain Chart" >
<p align="center" id="fig1">[Figura 1] Core Domain Chart</p>
</div>

Per i sottodomini individuati è stato realizzato il *Core Domain Chart* mostrato in <a href="#fig1">Figura 1</a> il quale mostra come i sottodomini si posizionano rispetto ai due fattori di "business value" e "complessità del modello del dominio".
Il "business value" si riferisce al valore distintivo che un determinato aspetto del progetto porta rispetto agli altri, indica quindi cosa rende l'azienda unica e attraente per i suoi clienti o utenti. La "complessità del modello del dominio" riflette quanto sia complesso il sistema sottostante che gestisce e rappresenta i concetti incorporati nel sottodominio considerato.
I sottodomini identificati sono quindi stati disposti nel *Core Domain Chart* in base alla loro business value e complessità del modello del dominio. Inoltre, qui di seguito è riportata la possibile evoluzione di questi sottodomini nel corso di 1-2 anni dalla fase iniziale di completamento del progetto, considerando anche miglioramenti futuri:
- percorsi: attualmente considerato core;
- marcatori: attualmente considerato supporting;
- coupon: attualmente considerato supporting. Tra 1-2 anni diventano supporting con maggiore rilevanza nel business e complessità aggiungendo percorsi sponsorizzati da aziende che mettono a disposizione premi coupon;
- utenti: attualmente considerato supporting;
- dati ambientali: attualmente considerato generic. Tra 1-2 anni diventano supporting aggiungendo AI per capire le condizioni dei monumenti/punti di interesse, quindi suggerire manutenzioni o azioni correttive. Inoltre si potrebbero consigliare/modificare percorsi in base alle condizioni ambientali (ad esempio, se piove evitare certe tappe o consigliare percorsi fitness con qualità d'aria maggiore).