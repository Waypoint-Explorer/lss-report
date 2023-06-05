---
layout: default
title: Sottodomini
parent: Analisi del Dominio
nav_order: 2
---

# Sottodomini
Sottodomini trovati:
- percorsi: si occupa della gestione dei percorsi (aggiunta, modifica, eliminazione) e delle loro tappe
- marcatori: si occupa della gestione dei marcatori (aggiunta, modifica, eliminazione) e delle loro condizioni (corretto funzionamento, errori, guasti)
- coupon: si occupa della gestione dei coupon (aggiunta, eliminazione, validità)
- utenti: si occupa della gestione degli utenti (aggiunta, gestione dello storico)
- dati ambientali: si occupa della gestione dei dati ambientali, della visualizzazione e analisi delle informazioni

<div align="center">
<img src="../../img/core-domain-chart.svg" alt="Core Domain Chart" >
<p align="center" id="fig">[Fig ] Core Domain Chart</p>
</div>

Analisi specifica dei sottodomini in base alla loro business value e complessità del modello del dominio:
- percorsi: attualmente considerato core
- marcatori: attualmente considerato supporting
- coupon: attualmente considerato supporting. Tra 1-2 anni diventano supporting con maggiore rilevanza nel business e complessità aggiungendo percorsi sponsorizzati da aziende che mettono a disposizione premi coupon.
- utenti: attualmente considerato supporting
- dati ambientali: attualmente considerato generic. Tra 1-2 anni diventano supporting aggiungendo AI per capire le condizioni dei monumenti/punti di interesse, quindi suggerire manutenzioni o azioni correttive. Inoltre si potrebbero consigliare/modificare percorsi in base alle condizioni ambientali (es. se piove evitare certe tappe o consigliare percorsi fitness con qualità aria maggiore)