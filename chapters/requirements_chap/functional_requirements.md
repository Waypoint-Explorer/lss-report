---
layout: default
title: Requisiti Funzionali
parent: Requisiti
nav_order: 2
---

# Requisiti Funzionali
I requisiti funzionali sono le specifiche funzionalità e comportamenti che un sistema deve avere per essere ritenuto corretto. Essi sono scaturiti da un'analisi approfondita dei requisiti utente e sono una guida durante lo sviluppo del sistema, per controllare che siano stati rispettate le richieste del committente. Sono in seguito analizzate le funzionalità dei diversi componenti del sistema: applicazione utente, applicazione amministrazione comunale e dispositivo.

1. visualizzare i possibili percorsi sulla mappa
   1. selezionare una località in cui effettuare percorsi
       - selezionare automaticamente la località in cui ci si trova tramite posizione GPS
       - selezionare manualmente la località tramite una barra di ricerca
   2. mostrare le tappe che compongono i percorsi
      - mostrare l'ordine consigliato delle tappe che compongono un percorso 
   3. mostrare i percorsi diversamente secondo la loro tipologia
   4. filtrare i percorsi per tipologia: culturale, tematico, naturalistico, turistico, fitness

2. selezione e avvio di un percorso tra quelli disponibili
    1. visualizzare i dettagli del percorso selezionato
       - visualizzare la categoria del percorso
       - visualizzare la descrizione del percorso se presente
       - visualizzare le informazioni aggiuntive sulle tappe del percorso
            - descrizione
            - via o località
            - posizione geografica
            - orari di apertura se presenti
            - prezzo, se il punto di interesse è a pagamento
            - informazioni sull'accessibilità del punto di interesse
        - visualizzare i punti extra forniti al completamento del percorso
    1. avvio del percorso selezionato

3. navigazione tra le tappe di un percorso
    1. mostrare la tappa successiva consigliata
    2. mostrare le tappe nelle vicinanze anche se non incluse nel percorso selezionato
    3. scansionare il codice QR di una tappa
    4. terminare un percorso:
        - premendo un pulsante in qualsiasi momento del percorso
        - consigliando all'utente di terminare il percorso con un pulsante al completamento di un percorso (può anche continuare ad effettuare una visita e terminare in seguito il percorso)

4. visualizzare il riepilogo del percorso concluso
    1. visualizzare un riepilogo quando si completa un percorso, inserendo:
        - le tappe visitate
        - punteggio totale ottenuto
        - tempo impiegato

5. effettuare la registrazione di un utente guest
   1. effettaure la registrazione inserendo:
        - obbligatori: nome utente, password, email, Paese di residenza
        - facoltativi: città di residenza, anno di nascita

6. effettuare il login utente
   1. effettuare il login inserendo nome utente e password

7. convertire in coupon sconto i punti accumulati completando i percorsi
    1. visualizzare totale punti disponibili
    2. visualizzare tutti i coupon disponibili
    3. visualizzare coupon riscattati

8. visualizzare lo storico dei percorsi effettuati in precedenza
    1. visualizzare numero percorsi effettuati
    2. visualizzare i dettagli dei percorsi effettuati
        - data del percorso
        - tappe del percorso
        - punti ottenuti nel percorso

9. effettuare l'accesso al sistema tramite credenziali fornite come amministratore
   1. effettuare l'accesso e visualizzare il menu amministrazione

10. gestire i marcatori
    1. aggiungere un marcatore al sistema inserendo un suo identificativo, le coordinate geografiche del punto di installazione e il tipo. Nel caso in cui il marcatore sia un dispositivo, si può inserire anche un punteggio ottenibile

11. gestire le tappe
    1. aggiungere una tappa
        - inserendo il nome
        - associando un marcatore
        - inserendo alcune informazioni aggiuntive opzionali
            - descrizione
            - via o località
            - posizione geografica
            - orari di apertura
            - prezzo, se il punto di interesse è a pagamento
            - informazioni sull'accessibilità del punto di interesse

12. visualizzare le informazioni riguardanti i dispositivi
    1. visualizzare i dati raccolti dai sensori di temperatura, pressione, umidità e qualità dell'aria
    2. visualizzare se sono presenti guasti

13. gestire i percorsi suggeriti
    1. creare un percorso inserendo:
       - il nome
       - la categoria
       - le tappe che dovranno essere visitate
       - i punti extra che è possibile ottenere completando il percorso
       - la descrizione (opzionale)
        
14. gestire i coupon
    1. creare un coupon inserendo:
       - il titolo
       - l'attività commerciale che lo mette a disposizione
       - il numero di punti necessari per ottenerlo
       - descrizione facoltativa (include informazioni come la validità, le condizioni, il valore, etc.)

15. mostrare nel display del dispositivo il codice QR
    1. mostrare il codice QR contenente diverse informazioni:
        - codice univoco per identificare il dispositivo
        - codice univoco di controllo
        - dati dei sensori di temperatura, pressione, umidità e qualità dell'aria
        - informazioni del suo stato per identificare guasti

16. mostrare nel display i dati ambientali rilevati in quel momento
    1. mostrare data e misure

17. raccogliere dati ambientali periodicamente includendo:
    1. timestamp della misura
    2. dati ambientali
        - temperatura
        - umidità
        - pressione
        - qualità dell'aria

18. visualizzare informazioni riguardanti il progetto
    1. visualizzare informazioni generali del progetto
    2. visualizzare guida utente

19. statistiche per l'amministrazione
    1. statistiche sui percorsi effettuati dagli utenti nell'ultima settimana, nell'ultimo mese e nell'ultimo anno