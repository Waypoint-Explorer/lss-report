---
layout: default
title: Sottodomini
parent: Analisi del Dominio
nav_order: 2
---

# Sottodomini
Sottodomini trovati:
- percorsi: si occupa della creazione dei percorsi, aggiunta di tappe ad un percorso, creazione delle tappe, aggiunta di un marcatore ad una tappa, esecuzione di un percorso;
- marcatori: si occupa dell'inserimento nel sistema dei marcatori;
- coupon: si occupa dell'aggiunta di nuovi coupon e del riscatto dei coupon da parte degli esploratori;
- utenti: si occupa della registrazione di un nuovo utente esploratore, gestione dello storico degli utenti esploratori, accesso degli utenti esploratori e amministratori;
- dati ambientali: si occupa della gestione dei dati ambientali relativi ad un territorio (rilevazione, aggiunta e analisi dei dati).

<div align="center">
<img src="../../img/core-domain-chart.svg" alt="Core Domain Chart" >
<p align="center" id="fig">[Fig ] Core Domain Chart</p>
</div>

Analisi specifica dei sottodomini in base alla loro business value e complessità del modello del dominio:
- percorsi: attualmente considerato core;
- marcatori: attualmente considerato supporting;
- coupon: attualmente considerato supporting. Tra 1-2 anni diventano supporting con maggiore rilevanza nel business e complessità aggiungendo percorsi sponsorizzati da aziende che mettono a disposizione premi coupon;
- utenti: attualmente considerato supporting;
- dati ambientali: attualmente considerato generic. Tra 1-2 anni diventano supporting aggiungendo AI per capire le condizioni dei monumenti/punti di interesse, quindi suggerire manutenzioni o azioni correttive. Inoltre si potrebbero consigliare/modificare percorsi in base alle condizioni ambientali (ad esempio, se piove evitare certe tappe o consigliare percorsi fitness con qualità d'aria maggiore).