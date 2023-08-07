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
