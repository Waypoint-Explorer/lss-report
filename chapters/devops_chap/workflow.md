---
layout: default
title: Workflow
parent: DevOps
nav_order: 1
---

# Workflow

Il workflow impiegato per gestire lo sviluppo continuo del software e il suo rilascio si ispira al modello di Gitflow, incorporando alcune delle sue caratteristiche principali ma non adottandone integralmente l'approccio.\
Il modello Gitflow prevede che siano presenti due branch principali ```master``` e ```develop``` utilizzati rispettivamente per mantenere le versioni stabili rilasciate del software e per lo sviluppo del software.
Dal branch di sviluppo ```develop``` vengono poi creati dei branch specifici per l'implementazione di una nuova feature o per effettaure miglioramenti del codice che rimarranno attivi solamente per il tempo necessario allo sviluppo della funzionalità richiesta.
Prima del rilascio ufficiale di una versione stabile del codice vengono creati dei release branches a partire dal codice presente in ```develop``` nei quali vengono effettuati test e correzioni prima della release.
Nel caso in cui alcuni bug o problemi non vengano individuati durante il controllo effettuato nelle release branches finendo così nel codice rilasciato, vengono utilizzati dei branches di hotfix a partire da ```master``` con lo scopo di correggere il difetto e apportare infine le modifiche necessarie sia sul branch ```master``` che su ```develop```.\
Nel contesto di questo progetto il workflow utilizzato presenta, come Gitflow, due branch principali chiamati ```main``` e ```dev``` che rappresentano anche in questo caso il codice considerato rilasciato e stabile e il codice utilizzato per lo sviluppo. Sempre in maniera simile a Gitflow sono stati utilizzati branch distinti per ciascuna feature implementata a partire dal codice presente su ```dev``` per consentire a ciascun membro del team di lavorare in maniera isolata su di una specifica funzionalità per poi unire il codice su ```dev``` una volta completato lo sviluppo.
Generalmente il lavoro eseguito su un feature branch è pensato per essere completato da un solo sviluppatore nel corso di un breve arco temporale che solitamente richiede poche ore o al massimo pochi giorni lavorativi nel caso di feature più consistenti. In particolare, per questo progetto, è stato deciso di creare un feature branch per ogni requisito funzionale di secondo livello, ovvero, per ogni funzionalità individuata durante la fase di analisi dei requisiti sono stati individuati del task che implementano un aspetto parziale della macro funzionalità e per ciascuno di questi task è stato creato quindi creato un branch specifico per l'implementazione.
La prima differenza con il modello di Gitflow è il fatto di non aver utilizzato un branch specifico per la release del codice, effettuando quindi i test finali direttamente nel branch ```dev``` prima di spostare il codice nel branch ```main``` per il rilascio.
Un'ulteriore modifica rispetto al modello di Gitflow è l'assenza di branch per gli hotfix risolvendo i bug trovati direttamente nella feature branch relativa alla funzionalità che presenta l'errore mantenendo così il contesto e la continuità all'interno del lavoro su quella specifica funzionalità.

## Repository