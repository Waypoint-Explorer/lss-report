---
layout: default
title: Requisiti Non Funzionali
parent: Requisiti
nav_order: 4
---

# Requisiti Non Funzionali
I requisiti non funzionali rappresentano le caratteristiche e gli attributi aggiuntivi richiesti dal committente, che vanno al di là dei requisiti funzionali che specificano le funzionalità necessarie per garantire il corretto funzionamento del sistema. Mentre i requisiti funzionali si concentrano su ciò che il sistema deve fare, i requisiti non funzionali si concentrano su come il sistema deve comportarsi e rispondere in termini di prestazioni, affidabilità, sicurezza, usabilità e altre qualità che contribuiscono alla sua efficienza complessiva.

- Garantire il funzionamento dell'applicazione web su diversi browser, nello specifico: Chrome, Edge, Vivaldi, Opera;
- Interfaccia grafica accessibile agli utenti daltonici secondo standard WCAG (Web Content Accessibility Guidelines);
- Interfaccia grafica reattiva: alle azioni di un utente devono corrispondere degli aggiornamenti dell’interfaccia stessa in tempi ragionevoli (al massimo un secondo) per non rovinare la user experience;
- Interfaccia grafica intuitiva, che fornisca feedback coerenti all’utente per comunicargli lo stato delle sue azioni e coerente con gli standard di user experience di Material;
- Garantire tempi di risposta del sistema inferiori ai 10 secondi, supponendo che l'utente disponga di una connessione con banda sufficiente (50ms ping, 20Mbps download, 5Mbps upload);
- Il sistema dovrà essere in grado di memorizzare dati di interesse in maniera consistente;
- Il sistema deve essere fault-tolerant, cioè deve continuare a funzionare in modo affidabile e non deve mai interrompersi qualora si verifichi un errore, ma proseguire senza generare fallimenti. In particolare deve gestire correttamente le seguenti problematiche:
    - inserimento di dati errati (credenziali errate, valori non ammessi nei campi di un form, etc.);
    - assenza temporanea della connessione internet durante l'uso del sistema.