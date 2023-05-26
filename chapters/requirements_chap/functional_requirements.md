---
title: Requisiti Funzionali
parent: Requisiti
nav_order: 3
---

# Requisiti Funzionali
I requisiti funzionali sono le specifiche funzionalità e comportamenti che un sistema deve avere per essere ritenuto corretto. Essi sono scaturiti da un'analisi approfondita dei requisiti utente e sono una guida durante lo sviluppo del sistema, per controllare che siano stati rispettate le richieste del committente. Sono in seguito analizzate le funzionalità dei diversi componenti del sistema: applicazione utente, applicazione amministrazione comunale e dispositivo.

## Applicazione Utente
1. visualizzare i possibili percorsi sulla mappa
   1. selezionare una località in cui effettuare percorsi
       1. selezionare automaticamente la località in cui ci si trova tramite posizione GPS
       2. selezionare manualmente la località tramite la barra di ricerca
   2. mostrare le tappe che compongono i percorsi
      1. mostrare l'ordine consigliato delle tappe che compongono un percorso
   3. mostrare i percorsi diversamente secondo la loro tipologia
   4. filtrare percorsi visualizzando e selezionare le tipologie di percorsi, esse possono distinguersi in:-
      - culturale: percorsi che includono elementi di vario tipo del patrimonio culturale di una zona (teatri, musei, mausolei, tombe, chiese, statue, etc.)
      - tematico: percorsi che includono punti di interesse che riguardano uno specifico tema (luoghi che hanno ispirato un autore, luoghi che sono legati ad un personaggio famoso, edifici di un architetto, monumenti di una certa epoca storica, etc.)
      - naturalistico: percorsi che includono elementi naturali presenti nel territorio (parchi, spiagge, sentieri, fiumi, etc.)
      - turistico: percorsi che includono le attrazioni turistiche principali di una città (fontana, piazza, mercati, musei, viali, etc.)
      - fitness: percorsi che non necessariamente includono punti di interesse storico-culturali-naturalistici, generalmente sono più lunghi con lo scopo di effettuare esercizio fisico (camminate, percorsi ciclabili, etc.)                

2. selezione e avvio di un percorso tra quelli disponibili
    1. visualizzare i dettagli del percorso selezionato
       1. visualizzare la categoria del percorso
       2. visualizzare la descrizione del percorso se presente
       3. visualizzare le informazioni aggiuntive sulle tappe del percorso
            1. via o posizione geografica
            2. orari di apertura se presenti
            3. prezzo se il punto di interesse è a pagamento
            4. informazioni sull'accessibilità del punto di interesse

3. navigazione tra le tappe di un percorso
    1. mostrare la tappa successiva consigliata
    2. mostrare le tappe nelle vicinanze anche se non incluse nel percorso selezionato
    3. scansione del codice QR di una tappa
    4. terminare un percorso:
        1. premendo un pulsante in qualsiasi momento del percorso
        2. consigliando all'utente di terminare il percorso con un pulsante al completamento di un percorso (può anche continuare ad effettuare una visita e terminare in seguito il percorso)

4. visualizzare il riepilogo del percorso concluso
    1. riepilogo di tutte le tappe visitate
    2. punteggio totale ottenuto
    3. tempo impiegato

5. effettuare la registrazione di un utente inserendo alcuni dati:
    - obbligatori: nome utente, password, email, Paese
    - facoltativi: città, anno di nascita

6.  effettuare il login utente inserendo email e password

7.  convertire in coupon sconto i punti accumulati completando i percorsi
    1. visualizzare totale punti disponibili
    2. visualizzare tutti i coupon disponibili

8.  visualizzare lo storico dei percorsi effettuati in precedenza
    1. visualizzare numero percorsi effettuati
    2. visualizzare i dettagli dei percorsi effettuati
        1. data percorso
        2. tempo del percorso
        3. tappe del percorso
        4. punti ottenuti nel percorso

## Applicazione Amministrazione Comunale
1. effettuare l'accesso al sistema tramite credenziali fornite

2. gestire i marcatori
    1. aggiungere un dispositivo al sistema inserendo le coordinate geografiche del punto di installazione
    2. eliminare un dispositivo

3. gestire le tappe
    1. aggiungere una tappa:
        1. associando un marcatore
        2. inserendo alcune informazioni aggiuntive opzionali:
            - via o posizione geografica
            - orari di apertura
            - prezzo se il punto di interesse è a pagamento
            - informazioni sull'accessibilità del punto di interesse
        3. inserendo il punteggio ottenibile
    2. modificare una tappa:
        1. modificando un marcatore
        2. modificando alcune informazioni aggiuntive opzionali:
            - via o posizione geografica
            - orari di apertura
            - prezzo se il punto di interesse è a pagamento
            - informazioni sull'accessibilità del punto di interesse
        3. modificando il punteggio ottenibile
    3. eliminare una tappa

4. visualizzare le informazioni riguardanti i dispositivi
    1. visualizzare i dati raccolti dai sensori di temperatura, pressione, umidità e qualità dell'aria
    2. visualizzare il numero di utenti che hanno visitato il punto di interesse collegato al dispositivo, cioè quanti hanno scansionato un codice QR in quella determinata tappa
    3. visualizzare se sono presenti guasti

5. creare dei percorsi suggeriti inserendo:
    - la categoria
    - le tappe che dovranno essere visitate
    - i punti extra che è possibile ottenere completando il percorso
        
6. creare i coupon inserendo:
    - le attività commerciali che li mettono a disposizione
    - descrizione del coupon (include informazioni come la validità, le condizioni, il valore, etc.)
    - il numero di punti necessari per ottenerli
        
## Dispositivo
1. mostrare nel display il codice QR, il quale contiene diverse informazioni:
    1. codice univoco per identificare il dispositivo
    2. codice univoco di controllo
    3. dati dei sensori di temperatura, pressione, umidità e qualità dell'aria
    4. informazioni del suo stato per identificare guasti 
2. mostrare nel display i dati ambientali rilevati in quel momento