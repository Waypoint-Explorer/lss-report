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
Un'ulteriore modifica rispetto al modello di Gitflow è l'assenza di branch per gli hotfix risolvendo i bug trovati direttamente nella feature branch relativa alla funzionalità che presenta l'errore mantenendo così il contesto e la continuità all'interno del lavoro su quella specifica funzionalità.\
Lo schema riassuntivo di Figura X riporta il workflow che è stato concordato dal team di sviluppo  mostrando alcuni dei possibili scenari che potrebbero verificarsi durante l'implementazione del sistema.

<div align="center">
    <img src="../../img/workflow.png" alt="Workflow del progetto">
    <p align="center" id="fig99">[Fig ] Workflow del progetto</p>
</div>

Durante lo sviluppo di questo progetto è stato adottato Semantic Versioning (SemVer v2) per etichettare le diverse versioni del software rilasciato. Ciascuna versione del codice è quindi numerata secondo la struttura MAJOR.MINOR.PATCH dove, rispettivamente, il numero di PATCH riflette il rilascio delle correzioni di bug, il numero di MINOR indica il rilascio di nuove funzionalità compatibili, mentre il numero di MAJOR denota cambiamenti radicali che potrebbero comportare incompatibilità con versioni precedenti.\
Nell'assegnare un numero di versione al codice del progetto ci siamo tuttavia focalizzati più sulle funzionalità implementate che sull'interfaccia presente nel codice dato che è stato ritenuto che legare il numero di versione strettamente al codice non avrebbe portato, in questo specifico caso, ad una chiara tracciabilità dei cambiamenti effettuati. Si è voluto quindi porre maggior attenzione sulle funzionalità implementate per rendere più intuitivo lo stato del progetto e nello specifico è stato utilizzato il numero di PATCH per tracciare bug fix o modifiche che non aggiungono nuove funzionalità, il numero di MINOR per tracciare l'implementazione delle task presenti requisiti funzionali che aggiungono quindi funzionalità per gli utenti del sistema e il numero di MAJOR per indicare cambiamenti importanti nella storia del progetto.\
Durante lo sviluppo di questo progetto, mentre il numero di PATCH e MINOR avevano un riscontro ben chiaro nel codice o nella documentazione di esso, il numero di MAJOR è stato utilizzato solamente per indicare la fine dello sviluppo di tutti i requisiti concordati. Qualora in futuro questo progetto cambi radicalmente la propria natura apportando quindi modifiche importanti alle proprie funzionalità questo verrebbe comunicato attraverso un incremento del numero MAJOR.

Il team di sviluppo ha inoltre deciso di seguire l'approccio descritto da Convetional Commit sia per rendere facilmente automatizzabile l'incremento del numero di versione sia per rendere più chiaro lo scopo del codice introdotto durante i commit strutturando il messaggio di commit nel seguente modo: ```<type>[optional scope]: <description>```
Ogni commit, oltre a includere una esplicativa descrizione di quanto implementato ed opzionalmente un riferimento alla porzione del progetto interessata dalle modifiche, è anche contrassegnato da un tipo selezionato da un elenco di opzioni, ognuna con un significato specifico distinto.
I tipi di commit utilizzati in questo progetto sono i seguenti:

**chore**: modifiche generiche che non aggiungono funzionalità\
**feat**: aggiunta di una nuova feature\
**fix**: risoluzione di un bug o incorrettezza generica\
**ci**: modifiche relative alla continous integration del progetto\
**docs**: modifiche che riguardano la documentazione del progetto

## Repository