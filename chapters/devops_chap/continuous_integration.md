---
layout: default
title: Continuous Integration
parent: DevOps
nav_order: 2
---

# Continuous Integration

## GitHub Actions
Sin da subito sono state inoltre utilizzate funzionalità di continous integration e
deployment del sistema. In particolare, grazie alle GitHub Actions, ad ogni modifica eseguita ed approvata sul codice sorgente corrisponde in automatico il rilascio
di una nuova versione dell’applicazione sotto forma di immagini Docker. Questo,
grazie ad un ulteriore container Docker che utilizza un’immagine chiamata Watchtower, permette di aggiornare il sistema in maniera automatica senza alcun
intervento esterno anche se il sistema si trova distribuito all’interno di un server
remoto.

### Dispositivo
Per quanto riguarda il dispositivo, sono stati realizzati due *workflow*. Il *Build* per compilare il codice e il *Relesase* per creare una nuova *release*. Di seguito verrà spiegato in dettaglio il loro funzionamento.
#### Build
Questo *workflow* viene eseguito ogni volta che si effettua una *push* da branch diversi dal *main*. Ha la possibilità di essere chiamato da altri *workflow*. È necessario per le *Branch protection rules*, perchè viene utilizzata dallo `Require status checks to pass before merging` verso i branch *main* e *dev*, in modo da poter fare il *merge* solo se la *build* viene completata con successo. \
Come illustrato in <a href="#device-workflow-build">Figura 1</a> è composto da un singolo *job* che si occupa di:
- Installare python e PlatformIO <a href="#1">[1]</a>;
- compilare il codice, scaricando tutte le dipendenze necessarie;
- archiviare il compilato come artefatto delle *GitHub Actions* per renderlo disponibile al download e condivisibile tra i *job*. 

<div align="center">
<img id="device-workflow-build" src="../../img/device-workflow-build.png" alt="Build workflow"  style="width: 15rem">
<p align="center">[Figura 1] Build workflow</p>
</div>

#### Release
Questo *workflow* viene eseguito solamente quando viene fatta una *push* al branch *main* ed è mostrato in <a href="#device-workflow-release">Figura 2</a>. È necessario per rilasciare in automatico una nuova *release* ogni volta che viene effettuata una *push* a *main*, come definito nel capitolo **Workflow**. \
I *job* che vengono eseguiti sono i seguenti:
1. *Call Build*: richiama il *workflow* di *Build*, precedentemente mostrato;
2. *Bump Tag*: dopo che è stato completato con successo il *job* di *Build*, si occupa della creazione del *tag*. Attraverso l'utilizzo della *Github Action* *anothrNick/github-tag-action* <a href="#2">[2]</a> è stato possibile formattare in automatico il *tag* rispettando il *Semantic Versioning* utilizzato nel progetto.
3. *Release*: dopo che i *job* precedenti sono stati completati con successo, viene eseguita la *release* su *GitHub Release*. Questa è composta del tag precedentemente creato, l'artefatto caricato dal *workflow* di *Build* e il codice sorgente.

<div align="center">
<img id="device-workflow-release" src="../../img/device-workflow-release.png" alt="Release workflow" >
<p align="center" >[Figura 2] Release workflow</p>
</div>

## Riferimenti
<a id="1">[1]</a> PlatformIO, https://platformio.org/ \
<a id="2">[2]</a> github-tag-action, https://github.com/anothrNick/github-tag-action