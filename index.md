---
title: Home
layout: home
---

# Waypoint Explorer

## Introduzione

Waypoint Explorer è un progetto nato per incentivare la visita dei punti di interesse turistici, culturali e naturalistici attraverso percorsi, con l'obiettivo di promuovere lo sviluppo del territorio e l'esercizio fisico all'aria aperta.

Il sistema prevede l'installazione di dispositivi in corrispondenza dei punti di interesse che si incontrano lungo il percorso. Questi dispositivi sono dotati di sensori in grado di rilevare le condizioni ambientali e mostrano un codice QR univoco che deve essere scansionato per poter procedere alla tappa successiva. I dispositivi sono progettati per funzionare in modo autonomo e con un basso consumo energetico, utilizzando eventualmente una batteria e un pannello solare. I percorsi saranno percorribili solamente a piedi, in bicicletta o con mezzi sostenibili come i monopattini elettrici, incentivando l'uso di mezzi di trasporto a basso impatto ambientale. Completando i percorsi, gli utenti saranno premiati con buoni sconto per incentivare l'uso del sistema e sostenere le attività locali.

Inoltre, l'amministrazione comunale avrà la possibilità di raccogliere informazioni sul territorio attraverso i sensori dei dispositivi, fornendo dati utili per la gestione dell'area e la pianificazione delle attività turistiche. Grazie alla sua scalabilità e alla sua flessibilità, il sistema potrà essere facilmente esteso e adattato alle esigenze specifiche di ogni territorio.

Daniele Gambaletta - daniele.gambaletta@studio.unibo.it - 0000924643\
Riccardo Omiccioli - riccardo.omiccioli@studio.unibo.it - 0001054475\
Cecilia Teodorani - cecilia.teodorani@studio.unibo.it - 0001032918

---

## Analisi del Dominio
La prima attività che è stata svolta durante lo sviluppo del progetto è l'analisi del dominio in cui si inserisce il progetto. Questa comprende un incontro con il committente, che ci si è immaginati il Comune di Ravenna. Inizialmente, la persona preposta dell'amministarazione comunale ha esposto l'idea generale del progetto e successivamente sono state effettuate delle domande e osservazioni per comprendere al meglio le esigenze. Durante la fase di analisi sono stati prodotti dei documenti per comprendere al meglio le esigenze.

### Knowledge Crunching
#### Intervista con il committente
"Ciao, sono un dipendete del Comune di Ravenna, mi occupo di ... . Grazie al Piano Nazionale di Ripresa e Resilienza (PNRR), sono stati stanziati dei fondi per la "Digitalizzazione, Innovazione, Competitività, Cultura" e noi abbiamo deciso di utilizzarli per un progetto nell'ambito di "Approccio digitale per il rilancio di turismo e cultura". Il nostro obiettivo è quello di incentivare la visita dei punti di interesse turistici, culturali e naturalistici, promuovendo al tempo stesso lo sviluppo del territorio e l'attività fisica all'aria aperta.

Esso si inserisce in un contesto in cui, dopo il periodo di Covid, sono tornati i turisti esteri a visitare il nostro Paese e anche noi italiani abbiamo ricominciato a vagare per i nostri territori. Contemporaneamente, a causa del cambiamento climatico in corso e alla sensibilizzazione effettuata nella popolazione mondiale, tutti i cittadini hanno una consapevolezza maggiore e si cerca di incentivare l'utilizzo di mezzi non inquinanti (come bicicletta o skateboard), sostenibili (quali i monopattini elettrici) o mezzi pubblici di trasporto (ad esempio gli autobus). Ancora meglio per la salute e l'ambiente sarebbe spostarsi a piedi, unendo così l'attività fisica all'aria aperta.

Durante una riunione preliminare nella nostra area, è emerso che potremmo creare dei percorsi che toccano vari punti di interesse, come ad esempio musei, monumenti, sentieri, panorami, piazze, con lo scopo di rendere piacevole, divertente e stimolante la visita del territorio.

In più, vorremmo incentivare l'acquisto nei negozi locali, quindi dobbiamo pensare ad un modo per aggiungere questo obiettivo al progetto. Ad esempio, pensavamo di accordarci con gli esercenti locali di fornire degli sconti a chi utilizza il sistema. Questo potrebbe incentivare ancora di più l'uso sistema."

Analista: "Cosa intendete come percorso?"
Domain Expert: "Un percorso è un itenerario composto da varie tappe. Ogni tappa si colloca in un punto di interesse del territorio."

Analista: "Cosa si intendete per punto di interesse?"
Domain Expert: "Un punto di interesse è tutto ciò che può interessare ad un visitatore: musei, monumenti, piazze, edifici rilvenati, punti panoramici, sentieri, parchi, etc."

Analista: "Chi e come crea i percorsi?"
Domain Expert: "Il Comune si occuperà di decidere tutti i percorsi con le relative tappe creando percorsi tematici, ad esempio i luoghi di Dante, i monumenti patrimonio dell'Unesco, i punti panoramici, i parchi e giardini pubblici."

Analista: "Quante tappe ci possono essere in un percorso?"
Domain Expert: "In un percorso ci deve essere almeno una tappa, ma non c'è un limite massimo. Nel caso in cui ci siano più tappe in un percorso, queste hanno un ordine ben preciso da rispettare."

Analista: "Come far navigare un utente tra le varie tappe di un percorso?"
Domain Expert: "Ci sarà una mappa che mostra i punti di interesse e un itinerario consigliato, ma l'utente è libero di scegliere il tragitto che ritiene più opportuno."

Analista: "Con quali mezzi di trasporto ci si può spostare tra i vari punti di interesse?"
Domain Expert: "Come accennato in precedenza, vogliamo incentivare l'attività fisica o comunque in generale il trasporto sostenibile. Per questo motivo vorremmo che l'utente si spostino a piedi, con mezzi di mobilità attiva (biciletta, skateboard, rollerblade), mezzi di micro mobilità elettrica (monopattini elettrici, biciclette a pedalata assistita, hoverboard e segway) o al massimo con i mezzi pubblici di trasporto."

Analista: "Dato che ha accennato all'incentivare l'acquisto nei negozi locali e sconti, questi ultimi con quale criterio vengono rilasciati?"
Domain Expert: "L'utente accumula un certo numero di punti predeterminato per ogni tappa che visita. Per incentivarlo a visitare luoghi meno conosciuti o più lontani, questi punti di interesse potrebbero avere un punteggio maggiore. L'utente può utilizzare i punti accumulati per sbloccare dei coupon di sconto per una serie di negozi. Addirittura, potremmo pensare di inserire questo meccanismo per fornire sconti anche per musei o luoghi culturali a pagamento presenti sul territorio."

Analista: ""
Domain Expert: ""

- come si immaginano il progetto? ""
- come controlalre che l'utente visiti una tappa
- visto che mettiamo dei dispositivi disseminati per il territorio, vi serve avere dei dati ambientali di quei luoghi? "OVVIO. Aiuterebbe molto anche per capire lo stato di inquinamento delle zone in cui sono presenti dei monumenti particolarmente sensibili alle condizioni ambientali (monitoraggio per l'usura)"
- con quali mezzi di trasporto ci si può spostare tra i vari punti di interesse?

#### Diagrammi dei casi d'uso
#### Diagrammi delle attività
#### Domain storytelling
#### Mock-up
### Sottodomini
### Ubiquitous Language

## Requisiti
  ### Requisiti di Business
    quello che vuole il comune committente
    caratteristiche che il sistema dovrà possedere per essere corretto
  ### Requisiti Utente
    funzionalita' viste dall'utente e user stories
  ### Requisiti Funzionali
  ### Requisiti non Funzionali
  ### Requisiti Implementativi

## Design Architetturale
  ### Bounded Context
  ### Context Map
  ### Architettura di Dettaglio

## Processo di Sviluppo

## DevOps

## Implementazione
  ### Dettagli Implementativi
  ### Deployment