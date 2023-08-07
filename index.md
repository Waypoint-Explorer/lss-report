---
title: Home
layout: home
has_children: false
nav_order: 1
---

# Waypoint Explorer
<div align="center">
<img src="./img/logo.svg" alt="Waypoint Explorer Logo" style="width: 20rem" >
<p align="center" id="logo">Waypoint Explorer Logo</p>
</div>

## Guida del progetto
La web app è disponibile su GitHub al seguente link: [Repository Explorer App](https://github.com/Waypoint-Explorer/explorer-app).\
Per installare la web app è possibile:
#### Costruire e avviare il progetto
- Ottenere il codice sorgente
- Creare e compilare il file ```.env``` secondo quanto specificato nel template ```.env-template```
- Avviare il progetto utilizzando uno dei seguenti comandi:
    - ```docker-compose -f docker-compose.yml up --build --remove-orphans```
    - ```npm start``` se si dispone di npm installato
#### Utilizzare l'ultima release delle immagini docker
- Ottenere il codice sorgente completo o il file ```docker-compose-auto.yml```
- Creare e compilare il file ```.env``` secondo quanto specificato nel template ```.env-template```
- Avviare il progetto utilizzando uno dei seguenti comandi:
    - ```docker-compose -f docker-compose-auto.yml up --build --remove-orphans --detach```
    - ```npm run deploy``` se si dispone di npm installato e del codice sorgente

Il codice del device è disponibile su GitHub al seguente link: [Repository Device](https://github.com/Waypoint-Explorer/device
)

## Componenti del gruppo
Daniele Gambaletta - <daniele.gambaletta@studio.unibo.it> - 0000924643\
Riccardo Omiccioli - <riccardo.omiccioli@studio.unibo.it> - 0001054475\
Cecilia Teodorani - <cecilia.teodorani@studio.unibo.it> - 0001032918