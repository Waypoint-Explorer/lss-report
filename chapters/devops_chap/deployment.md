---
layout: default
title: Deployment
parent: DevOps
nav_order: 3
---

# Deployment
Come già scritto nella parte relativa all'architettura del sistema è stato considerato, sin dalle prime fasi progettuali, un eventuale deployment su larga scala.
Riprendendo quanto mostrato in Figura 34, l’architettura per il deployment si
compone sempre dei tre macro componenti del sistema con l’aggiunta di un componente che funge da reverse proxy server per garantire il corretto accesso al sistema da client esterni. Questa è una architettura piuttosto diffusa nel mondo delle applicazioni web che può far fronte ad un discreto numero di utenti simultanei.
<div align="center">
<img src="../../img/architecture_remote.png" alt="Architettura del sistema completato" >
<p align="center" id="fig98">[Fig ] Architettura del sistema</p>
</div>
Tenendo a mente che si tratta di un progetto pensato per essere realizzato all’interno di una singola amministrazione comunale, probabilmente un’architettura del
genere potrebbe soddisfare in maniera adeguata il numero di utenti che potrebbero
utilizzare il sistema. Inoltre, il deploy di questo sistema per un numero contenuto
di utenti potrebbe essere effettuato mantenendo un costo molto limitato, considerando soprattutto l’ordine di grandezza del budget messo di solito a disposizione
dalle amministrazioni comunali per progetti di questa natura.\
L’effettiva installazione del sistema potrebbe anche essere effettuata inizialmente su un elaboratore già in possesso dell’amministrazione comunale che, se pur
con prestazioni ridotte, potrebbe garantire il funzionamento del sistema per una
fase di testing iniziale, con un numero di utenti ridotto. Sicuramente, per un utilizzo più intensivo del sistema, sarebbe però indicata l’installazione su un VPS
(Virtual Private Server) o l’uso di servizi di cloud computing dato che, questo
approccio garantirebbe, a discapito di un costo maggiore, una serie di benefici
molto importanti soprattutto in termini di scalabilità è disponibilità.\