---
layout: default
title: Ubiquitous Language
parent: Analisi del Dominio
nav_order: 3
---

# Ubiquitous Language
Da questo punto in avanti, i seguenti termini verranno utilizzati con il significato indicato nelle relative definizioni. Dal momento che ci si confronta con un committente della Pubblica Amministrazione, cioè il Comune di Ravenna, la documentazione è scritta in lingua italiana, mentre durante l'implementazione è utilizzata la lingua inglese, facendo riferimento ai termini corrispondenti.

|**Termine italiano**|**Termine inglese**|**Definizione**|
|--------------------|-------------------|---------------|
| - tappa <br /> - punto di interesse | waypoint | un luogo, sia esso all'aperto o al chiuso, situato in un territorio che detiene un valore significativo per l'amministrazione comunale, tanto da volerlo promuovere come meta di visita, ad esempio musei, monumenti storici, sentieri panoramici o piazze |
| - percorso <br /> - itinerario| itinerary | un tragitto che si compone di tappe, che possono essere seguite in modo sequenziale o senza un ordine preciso |
| tipo itinerario| itinerary type| il tipo di un itinerario, che può essere culturale, tematico, naturalistico, turistico o fitness |
| itinerario completato| completed itinerary| un tragitto effettuato da uno degli utenti (guest o esploratore). Può includere una serie di tappe non ripetute che appartengono a vari percorsi diversi |
| - storico percorsi <br/> - itinerari completati| completed itineraries| insieme di tutti gli itinerari completati da un esploratore |
| marcatore | marker | un elemento presente nel mondo fisico che viene utilizzato per identificare ed associare una tappa fisica con la sua controparte memorizzata nel sistema. Può assumere la forma di un dispositivo o un codice QR stampato |
| tipo marcatore| marker type| il tipo di un marcatore, che può essere un dispositivo o un codice QR
| dispositivo <br /> (marcatore) | device | un oggetto fisico che integra un display per la visualizzazione di un codice identificativo della tappa (codice QR) e dei sensori per il monitoraggio ambientale (temperatura, umidità, pressione atmosferica e qualità dell'aria). Essendo una tipologia di marcatore, esso è posizionato nelle vicinanze della tappa corrispondente |
| misurazione| measure| un rilevamento di dati ambientali che comprende le coordinate geografiche, la data e l'orario della rilevazione, insieme a una serie di dati correlati a un fenomeno ambientale |
| sensore (dispositivo) | environmental sensor | un modulo che converte un fenomeno fisico in un segnale elettrico interpretabile dal dispositivo |
| dati ambientali (dispositivo) | environmental data | insieme di dati raccolti dal sensore composti da: temperatura, pressione, umidità e qualità dell'aria |
| - posizione <br /> - GPS <br /> - coordinate geografiche <br /> (dispositivo) | - position <br /> - GPS | coordinate geografiche del dispositivo (latitudine e longitudine) |
| errori (dispositivo) | errors data | dati di errore per notificare possibili guasti del dispositivo |
| dati raccolti (dispositivo) | entry data | dati raccolti che comprendono i dati ambientali e la timestamp di quando sono stati rilevati |
| - codice QR stampato <br /> - marcatore QR | QR marker | un codice QR stampato, quindi statico. Essendo una tipologia di marcatore, esso è posizionato nelle vicinanze della tappa corrispondente |
| utente guest | guest user  | utilizzatore del sistema che non ha effettuato l'accesso e utilizza le funzionalità di base fornite |
| esploratore <br /> (utente) | explorer | utente generico che ha effettuato l'accesso al sistema, ma non amministrazione |
| amministratore <br /> (utente) | admin | utente che fa parte dell'amministrazione comunale e che ha effettuato l'accesso al sistema con le credenziali istituzionali |
| coupon | coupon | offerta che garantisce uno sconto su un prodotto o servizio presso un esercente convenzionato. Per poterlo ottenere, l'utente deve utilizzare i propri punti guadagnati |
| - codice sconto <br /> - coupon riscattato | redeemed coupon | coupon riscattato dall'utente, cioè un codice monouso |
| punti | explorer points | valuta virtuale utilizzata all'interno del sistema, si ottengono visitando tappe e completando percorsi, possono essere utilizzati per riscattare dei coupon che hanno lo stesso valore in punti |
| riscattare| redeem| acquisizione di un codice sconto da parte di un esploratore, utilizzando i propri punti disponibili|
| nome utente | username | identificativo univoco scelto dall'utente guest durante la registrazione, non necessariamente deve corrispondere al nome vero della persona |
| - tipologia <br /> - categoria <br /> (marcatore, percorso) | - type <br /> - category| possibile categoria di un marcatore (dispositivo oppure marcatore QR) o di un itinerario (culturale, tematico, turistico, naturalistico, fitness) |
| culturale <br /> (percorso) | cultural | percorso che include elementi di vario tipo del patrimonio culturale di una zona (teatri, musei, mausolei, tombe, chiese, statue, etc.) |
| tematico <br /> (percorso) | themed | percorso che include punti di interesse che riguardano uno specifico tema (luoghi che hanno ispirato un autore, luoghi che sono legati ad un personaggio famoso, edifici di un architetto, monumenti di una certa epoca storica, etc.) |
| naturalistico <br /> (percorso) | naturalistic | percorso che include elementi naturali presenti nel territorio (parchi, spiagge, sentieri, fiumi, etc.) |
| turistico <br /> (percorso) | turistic | percorso che include le attrazioni turistiche principali di una città (fontana, piazza, mercati, musei, viali, etc.) |
| fitness <br /> (percorso) | fitness | percorso che non necessariamente include punti di interesse storico-culturali-naturalistici, generalmente sono più lunghi con lo scopo di effettuare esercizio fisico (camminate, percorsi ciclabili, etc.) |