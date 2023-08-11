---
layout: default
title: Continuous Integration
parent: DevOps
nav_order: 2
---

# Continuous Integration
Uno degli aspetti che sono stati presi in considerazione durante le prime fasi implementative è quello riguardante la Continuous Integration per integrare regolamrnete e in maniera automatica il codice prodotto dai membri del team. Utilizzando questo approccio è possibile ridurre drasticamente i conflitti tra le parti di software sviluppate in maniera indipendende dal team permettendo inoltre di rilasciare frequentemente nuove funzionalità ed accorgersi rapidamente dell'eventuale presenza di errori su porzioni di codice molto più piccole e facilmente gestibili. Avendo strutturato lo sviluppo del sistema in maniera incrementale questo risulta molto semplice da applicare ottenendo inoltre preziosi feedback del sistema completo per valutare lo stato complessivo e apportare miglioramenti.

## GitHub Actions
Nel corso dello sviluppo di questo progetto, sono state impiegate le GitHub Actions come strumento chiave per il processo di continuous integration consentendo di automatizzare le attività, relative soprattutto alla pubblicazione della documentazione del progetto e al rilascio della web app e del software del device.

### Web App
Per la web app è stato realizzato un workflow con lo scopo di automatizzare il versionamento e il rilascio del codice. Il workflow si compone quindi di tre *jobs* da eseguire in maniera sequenziale che realizzano le seguenti funzioni:\
**Push tag**: crea un nuovo *tag* che presenta il numero della versione del software seguendo i principi di Semantic Versioning spiegati precedentemente. Sfrutta la GitHub action _anothrNick/github-tag-action_ per identificare nel messaggio della pull request che aggiunge il codice alla branch ```main``` un token che specifica il tipo di incremento del numero di versione da effettuare. Avendo sfruttato la convenzione già descritta in precedenza nella scrittura dei messaggi relativi ai vari commit è stato possibile utilizzare il tipo di commit ```feat``` e ```fix``` per incrementare rispettivamente il numero di MINOR e PATCH.
**Create release**: crea una nuova release sfruttando il numero di versione generato dal _job_ precedente includendo tutto il codice sorgente relativo.
**Build and push image**: esegue parallelamente la build delle immagini docker del frontend, backend e database utilizzando il Dockerfile relativo a ciascuno dei tre componenti e carica il package risultate sul registry ghcr.io associando ad ognuno di essi il numero di versione corretto.

Nelle immagini di Figura X e Figura Y vengono ripresi il workflow per la release della web app e il risultato della pubblicazione dei package relativi al frontend dell'applicazione.

<div align="center">
    <img id="device-workflow-build" src="../../img/web-app-workflow.png" alt="Build workflow"  style="width: 50rem">
    <p align="center">[Figura ] Web App release workflow</p>
</div>

<div align="center">
    <img id="device-workflow-build" src="../../img/frontend-ghcr.png" alt="Build workflow"  style="width: 30rem">
    <p align="center">[Figura ] Web App frontend package</p>
</div>


### Dispositivo
Per quanto riguarda il dispositivo, sono stati realizzati due *workflow*. Il *Build* per compilare il codice e il *Relesase* per creare una nuova *release*. Di seguito verrà spiegato in dettaglio il loro funzionamento.
#### Build
Questo *workflow* viene eseguito ogni volta che si effettua una *push* da branch diversi dal *main*. Ha la possibilità di essere chiamato da altri *workflow*. È necessario per le *Branch protection rules*, perchè viene utilizzata dallo `Require status checks to pass before merging` verso i branch *main* e *dev*, in modo da poter fare il *merge* solo se la *build* viene completata con successo. \
Come illustrato in <a href="#device-workflow-build">Figura 1</a> è composto da un singolo *job* che si occupa di:
- Installare python e PlatformIO <a href="#1">[1]</a>;
- compilare il codice, scaricando tutte le dipendenze necessarie;
- archiviare il compilato come artefatto delle *GitHub Actions* per renderlo disponibile al download e condivisibile tra i *job*.

<div align="center">
<img id="device-workflow-build" src="../../img/device-workflow-build.jpg" alt="Build workflow"  style="width: 15rem">
<p align="center">[Figura 1] Build workflow</p>
</div>

#### Release
Questo *workflow* viene eseguito solamente quando viene fatta una *push* al branch *main* ed è mostrato in <a href="#device-workflow-release">Figura 2</a>. È necessario per rilasciare in automatico una nuova *release* ogni volta che viene effettuata una *push* a *main*, come definito nel capitolo **Workflow**. \
I *job* che vengono eseguiti sono i seguenti:
1. *Call Build*: richiama il *workflow* di *Build*, precedentemente mostrato;
2. *Bump Tag*: dopo che è stato completato con successo il *job* di *Build*, si occupa della creazione del *tag*. Attraverso l'utilizzo della *Github Action* *anothrNick/github-tag-action* <a href="#2">[2]</a> è stato possibile formattare in automatico il *tag* rispettando il *Semantic Versioning* utilizzato nel progetto.
3. *Release*: dopo che i *job* precedenti sono stati completati con successo, viene eseguita la *release* su *GitHub Release*. Questa è composta del tag precedentemente creato, l'artefatto caricato dal *workflow* di *Build* e il codice sorgente.

<div align="center">
<img id="device-workflow-release" src="../../img/device-workflow-release.jpg" alt="Release workflow" >
<p align="center" >[Figura 2] Release workflow</p>
</div>

## Riferimenti
<a id="1">[1]</a> PlatformIO, https://platformio.org/ \
<a id="2">[2]</a> github-tag-action, https://github.com/anothrNick/github-tag-action