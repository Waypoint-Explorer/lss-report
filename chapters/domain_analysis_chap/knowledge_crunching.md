---
title: Knowlede Crunching
parent: Analisi del Dominio
nav_order: 1
---

# Knowlede Crunching
## Intervista con il committente
"Ciao, sono un dipendete del Comune di Ravenna, mi occupo di ... . Grazie al Piano Nazionale di Ripresa e Resilienza (PNRR), sono stati stanziati dei fondi per la "Digitalizzazione, Innovazione, Competitività, Cultura" e noi abbiamo deciso di utilizzarli per un progetto nell'ambito di "Approccio digitale per il rilancio di turismo e cultura". Il nostro obiettivo è quello di incentivare la visita dei punti di interesse turistici, culturali e naturalistici, promuovendo al tempo stesso lo sviluppo del territorio e l'attività fisica all'aria aperta.\
Esso si inserisce in un contesto in cui, dopo il periodo di Covid, sono tornati i turisti esteri a visitare il nostro Paese e anche noi italiani abbiamo ricominciato a vagare per i nostri territori. Contemporaneamente, a causa del cambiamento climatico in corso e alla sensibilizzazione effettuata nella popolazione mondiale, tutti i cittadini hanno una consapevolezza maggiore e si cerca di incentivare l'utilizzo di mezzi non inquinanti (come bicicletta o skateboard), sostenibili (quali i monopattini elettrici) o mezzi pubblici di trasporto (ad esempio gli autobus). Ancora meglio per la salute e l'ambiente sarebbe spostarsi a piedi, unendo così l'attività fisica all'aria aperta.\
Durante una riunione preliminare nella nostra area, è emerso che potremmo creare dei percorsi che toccano vari punti di interesse, come ad esempio musei, monumenti, sentieri, panorami, piazze, con lo scopo di rendere piacevole, divertente e stimolante la visita del territorio.\
In più, vorremmo incentivare l'acquisto nei negozi locali, quindi dobbiamo pensare ad un modo per aggiungere questo obiettivo al progetto. Ad esempio, pensavamo di accordarci con gli esercenti locali di fornire degli sconti a chi utilizza il sistema. Questo potrebbe incentivare ancora di più l'uso sistema."

---
Analista: "Cosa intendete come percorso?"\
Esperto del Dominio: "Un percorso è un itenerario composto da varie tappe. Ogni tappa coincide con un punto di interesse del territorio."

Analista: "Cosa si intendete per punto di interesse?"\
Esperto del Dominio: "Un punto di interesse è tutto ciò che detiene un valore significativo per l'amministrazione comunale, tanto da volerlo promuovere come meta di visita: musei, monumenti, piazze, edifici rilevanti, punti panoramici, sentieri, parchi, etc."

Analista: "Chi e come crea i percorsi?"\
Esperto del Dominio: "Il Comune si occuperà di decidere quali sono i punti di interesse all'interno del proprio territorio che corrispondono alle tappe dei percorsi. Utilizzando le tappe inserite nel sistema, il Comune può creare dei percorsi suddivisi in categorie che verranno suggeriti ai visitatori, ad esempio percorsi culturali, tematici e naturalistici."

Analista: "Il visitatore dovrà necessariamente seguire per intero un percorso? Potrà interromperlo prima della fine? Potrà visitare altri punti di interesse che non sono all'interno del percorso scelto?"\
Esperto del Dominio: "No, l'utente potrà scegliere di effettuare solo una parte del percorso scelto, cioè può terminarlo in qualsiasi momento. In più, se dovesse scegliere di aggiungere altre tappe che non sono incluse nel percorso, può farlo liberamente e poi continuare con il percorso scelto inizialmente."

Analista: "Quante tappe ci possono essere in un percorso?"\
Esperto del Dominio: "In un percorso ci deve essere almeno una tappa, ma non c'è un limite massimo. Nel caso in cui ci siano più tappe in un percorso, queste non hanno un ordine preciso da rispettare."

Analista: "Come far navigare un utente tra le varie tappe di un percorso?"\
Esperto del Dominio: "Ci sarà una mappa che mostra i punti di interesse e un itinerario consigliato, ma l'utente è libero di scegliere il tragitto che ritiene più opportuno."

Analista: "Con quali mezzi di trasporto ci si può spostare tra i vari punti di interesse?"\
Esperto del Dominio: "Come accennato in precedenza, vogliamo incentivare l'attività fisica o comunque in generale il trasporto sostenibile. Per questo motivo vorremmo che l'utente si spostino a piedi, con mezzi di mobilità attiva (biciletta, skateboard, rollerblade), mezzi di micro mobilità elettrica (monopattini elettrici, biciclette a pedalata assistita, hoverboard e segway) o al massimo con i mezzi pubblici di trasporto."

Analista: "Cosa succede quando un utente termina un percorso?"\
Esperto del Dominio: "Il visitatore visualizza un riepilogo del percorso appena concluso. Vorremmo che gli utenti registrati possano visualizzare anche a posteriori i percorsi effettuati con le relative informazioni."

Analista: "Quindi consideriamo che ci possano essere sia utenti registrati che non?"\
Esperto del Dominio: "Chiunque può utilizzare alcune funzionalità del sistema, cioè visualizzare ed effettuare i percorsi. Se però un utente si registra, ha a disposizione più funzionalità e vantaggi: lo storico dei percorsi e gli sconti. Per la registrazione, bastano username, città di residenza, Stato, anno di nascita, indirizzo e-mail e password di accesso."

Analista: "Dato che ha accennato all'incentivare l'acquisto nei negozi locali e sconti, questi ultimi con quale criterio vengono rilasciati?"\
Esperto del Dominio: "L'utente accumula un certo numero di punti predeterminato per ogni tappa che visita e, completando interamente il percorso, ottiene punti extra. Per incentivarlo a visitare luoghi meno conosciuti o più lontani, questi punti di interesse potrebbero avere un punteggio maggiore. L'utente può utilizzare i punti accumulati per sbloccare dei coupon di sconto per una serie di attività commerciali. Addirittura, potremmo pensare di inserire questo meccanismo per fornire sconti anche per musei o luoghi culturali a pagamento presenti sul territorio."

Analista: "Come pensavate di far accumulare i punti all'utente e come può ottenere i coupon?"\
Esperto del Dominio: "Dopo che l'utente si è registrato, il sistema memorizza automaticamente il punteggio ottenuto, così che possa visualizzarlo e convertirlo in coupon validi per un singolo utilizzo."

Analista: "Visto che ogni tappa rilascia dei punti ai visitatori, avete pensato a come volete controllare che l'utente visiti veramente un punto di interesse?"\
Esperto del Dominio: "Sì, abbiamo pensato che in ogni luogo si potrebbe installare qualcosa per verificare che l'utente sia veramente passato da quella tappa. Avete in mente delle possibili soluzioni?"\
Analista: "Si potrebbe posizionare un codice QR in ogni punto di interesse e, quando l'utente lo scansiona, viene registrato il suo passaggio."

Esperto del Dominio: "Ora che ne stiamo parlando, sarebbe utile lato amministrativo poter monitorare il numero di visitatori per ogni tappa in un determianto lasso di tempo. In più, essendoci monumenti ad elevato rischio di usura causata dalle condizioni ambientali, c'è per caso modo di installare delle stazioni metereologiche nelle loro vicinanze?"\
Analista: "Potremmo pensare ad una soluzione che integri delle stazioni metereologiche e un display per il codice QR. In questo modo, potremmo generare un codice QR personalizzato per ogni visitatore per evitare che lo riutilizzino per accumulare punti senza veramente visitare la tappa. Avete già delle stazioni metereologiche a disposizione?"\
Esperto del Dominio: "Non ne abbiamo di preesistenti. Riuscite ad occuparvene voi?"\
Analista: "Certamente. Possiamo creare dei dispositivi che uniscono diversi sensori ambientali al display. Avete ncessità di alcune misurazioni specifiche?"\
Esperto del Dominio: "Ci interesserebbe ottenere informazioni riguardanti temperatura, umidità, pressione atmosferica e qualità dell'aria."

Analista: "Tutti i punti di interesse scelti dal Comune, hanno una copertura di rete e una fonte di alimentazione per la stazione metereologica?"\
Esperto del Dominio: "Purtroppo non possiamo assicurare queste caratteristiche, perché alcuni punti di interesse potrebbero trovarsi lontano dai centri abitati e/o immerso nella natura."

Analista: "Quindi per ogni tappa deve essere presente un dispositivo o possono esserci altri modi per identificare una tappa?"\
Esperto del Dominio: "Potrebbero esserci dei semplici codici QR stampati, tuttavia, considerando la necessità di un codice univoco per ogni visita al fine di evitare la riutilizzazione dei codici e l'ottenimento dei punti senza effettuare la visita, è possibile ipotizzare che le tappe che utilizzano un QR code stampato non assegnino punti agli utenti."

Analista: "Ora che abbiamo definito le caratteristiche generali, come vi immaginate il progetto?"\
Esperto del Dominio: "Pensavamo ad una applicazione del cellulare o ad un sito, visto che gli utenti devono poter utilizzare il servizio da smartphone all'esterno in giro per il territorio. Riassumendo quanto detto fino ad ora, il visitatore deve poter selezionare un percorso, vedere i punti di interesse sulla mappa per potersi orientare, scansionare il codice QR in ogni tappa, utilizzare i punti ottenuti per poter ricevere i coupon di sconto. L'amministrazione comunale deve poter monitorare la frequenza delle visite dei luoghi di interesse, le condizioni ambientali rilevate sul proprio territorio e lo stato delle stazioni metereologiche stesse."

## Diagrammi dei casi d'uso
A seguito dell'intervista con il committente e delle domande specifiche su alcuni aspetti, sono stati prodotti dei diagrammi dei casi d'uso. Essi hanno aiutato a schematizzare e rendere più chiaro quello che ogni attore del sistema deve poter fare.

Nel diagramma in <a href="#fig1">Figura 1</a> sono rappresentati sia i casi d'uso di un utente guest, cioè non autenticato, che quelli dell'utente registrato:
- utente:
  - visualizza tutta lista dei possibili percorsi
  - seleziona un percorso tra quelli visualizzati
  - arrivato ad una tappa, scansiona il relativo codice QR
  - effettua registrazione inserendo i propri dati
  - effettua login inserendo le proprie credenziali di accesso
- utente registrato:
  - converte in coupon sconto i punti accumulati completando i percorsi
  - visualizza storico percorsi effettuati in precedenza

<div align="center">
<img src="../../img/usecase-diagram-utente.svg" alt="Diagramma dei casi d’uso dell'utente" >
<p align="center" id="fig1">[Fig 1] Diagramma dei casi d’uso: utente</p>
</div>

Nel diagramma in <a href="#fig2">Figura 2</a> sono rappresentati i casi d'uso che riguardano l'area amministrativa del sistema:
- utente guest:
  - effettua il login per entrare nell'area riservata dell'amministrazione
- amministrazione comunale:
  - visualizza le informazioni relative allo stato e al funzionamento dei dispositivi (sensori e display)
  - visualizza le statistiche riguardanti le visite dei punti di interesse nel territorio
  - gestisce percorsi che comprendono una o più tappe
  - gestisce i coupon degli sconti, cioè inserisce dei possibili coupon da riscattare e decide quanti punti assegnare per ogni tappa
  - visualizza i dati sulle condizioni ambientali rilevati dai sensori
<div align="center">
<img src="../../img/usecase-diagram-comune.svg" alt="Diagramma dei casi d’uso dell'amministrazione comunale" >
<p align="center" id="fig2">[Fig 2] Diagramma dei casi d’uso: amministrazione comunale</p>
</div>

Nel diagramma in <a href="#fig3">Figura 3</a> sono rappresentati i casi d'uso relativi ai sensori utilizzati nel sistema di rilevamento e ai display:
- sensore:
  - raccoglie i dati ambientali effettuando le misurazioni
- display:
  - mostra il codice QR relativo ad una determinata tappa
<div align="center">
<img src="../../img/usecase-diagram-dispositivo.svg" alt="Diagramma dei casi d’uso del dispositivo" >
<p align="center" id="fig3">[Fig 3] Diagramma dei casi d’uso: dispositivo esterno</p>
</div>

## Domain storytelling
A seguito della lunga intervista effettuata con l'esperto del dominio e successivamente alla creazione degli schemi dei casi d'uso, sono stati approfonditi i concetti insieme al committente. Utilizzando la strategia del domain storytelling, sono stati realizzati i seguenti diagrammi per definire a fondo come i vari utilizzatori interagiscono passo per passo con il sistema.

<div align="center">
<img src="../../img/UsoUtente.svg" alt="" >
<p align="center" id="fig3">[Fig ] Utilizzo sistema parte utente</p>
</div>

<div align="center">
<img src="../../img/ModificaCredenziali.svg" alt="" >
<p align="center" id="fig3">[Fig ] Utente Modifica Credenziali</p>
</div>

<div align="center">
<img src="../../img/VisualizzazioneStoricoPercorsi.svg" alt="" >
<p align="center" id="fig3">[Fig ] Utente Visualizza Storico Percorsi</p>
</div>

<div align="center">
<img src="../../img/AcquistoCoupon.svg" alt="" >
<p align="center" id="fig3">[Fig ] Utente Acquista un coupon</p>
</div>

<div align="center">
<img src="../../img/CreazionePercorso.svg" alt="" >
<p align="center" id="fig3">[Fig ] Amministrazione crea un percorso</p>
</div>

<div align="center">
<img src="../../img/VisualizzazioneInformazioniDevice.svg" alt="" >
<p align="center" id="fig3">[Fig ] Amministrazione visualizza dati device</p>
</div>

<div align="center">
<img src="../../img/VisualizzazioneDatiAmbientali.svg" alt="" >
<p align="center" id="fig3">[Fig ] Amministrazione visualizza dati ambientali</p>
</div>

<div align="center">
<img src="../../img/VisualizzazioneStatisticheVisite.svg" alt="" >
<p align="center" id="fig3">[Fig ] Amministrazione visualizza statistiche visite</p>
</div>

<div align="center">
<img src="../../img/GestioneCoupon.svg" alt="" >
<p align="center" id="fig3">[Fig ] Amministrazione gestisce coupon</p>
</div>

<div align="center">
<img src="../../img/Device.svg" alt="" >
<p align="center" id="fig3">[Fig ] Device</p>
</div>

## Mock-up