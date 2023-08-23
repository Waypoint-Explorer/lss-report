---
layout: default
title: Requisiti Implementativi
parent: Requisiti
nav_order: 4
---

# Requisiti Implementativi
I requisiti implementativi specificano i dettagli che riguardano l'implementazione del sistema, concentrandosi sugli aspetti tecnici, linguaggi di programmazione, piattaforme e strumenti specifici necessari per sviluppare il software. I requisiti implementativi definiscono le linee guida e le specifiche tecniche che dovranno essere seguite durante tutto il processo di sviluppo per garantire un'implementazione efficace ed efficiente.

- Devono essere applicati i pattern del Domain Driven Design durante l'analisi, la progettazione e l’implementazione del sistema;
- La web app dovrà essere sviluppata utilizzando lo stack MEVN (*MongoDB* <a href="#1">[1]</a>, *Express* <a href="2">[2]</a>, *Vue.js* <a href="#3">[3]</a>, *Node.js* <a href="#4">[4]</a>) e *Typescript* <a href="#5">[5]</a>;
- Il sistema deve essere distribuito e testato su un server remoto;
- Il codice deve essere versionato con l'utilizzo di *Git* <a href="#6">[6]</a> con repository disponibile sull'hosting *GitHub* <a href="#7">[7]</a>;
- Per effettuare continuous integration e continuous deployment devono essere utilizzate le *GitHub Actions* <a href="#8">[8]</a> dove possibile;
- Per gestire il flusso di lavoro basato su *Git* deve essere utilizzato *Gitflow* e, in particolare, ogni feature branch deve essere utilizzata per sviluppare un requisito funzionale differente;
- Per identificare le versioni del software rilasciato deve essere utilizzato *Semantic Versioning* <a href="#9">[9]</a> 2.0.0.

## Riferimenti

<a id="1">[1]</a> MongoDB, https://www.mongodb.com/it-it

<a id="2">[2]</a> Express, https://expressjs.com/it/

<a id="3">[3]</a> Vue.js, https://vuejs.org/

<a id="4">[4]</a> Node.js, https://nodejs.org/en

<a id="5">[5]</a> Typescript, https://www.typescriptlang.org/

<a id="6">[6]</a> Git, https://git-scm.com/

<a id="7">[7]</a> GitHub, https://github.com/

<a id="8">[8]</a> GitHub Actions, https://github.com/features/actions

<a id="9">[9]</a> Semantic Versioning, https://semver.org/