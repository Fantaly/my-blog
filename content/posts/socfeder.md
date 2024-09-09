## Requisiti 

Il progetto nasce dalla necessità di gestire in modo più uniforme e automatizzato gli ordini e le offerte ricevuti via email. Ogni ordine/offerta contiene informazioni in un **formato sempre diverso** sui materiali. Le richieste principali che ho capito sono principalmente queste:

- La **prima richiesta** consiste nell'**estrarre le informazioni dalle offerte** (che arrivano principalmente tramite email e allegati in formato PDF, TXT, ecc..), salvarle nel database interno **e strutturarle uniformemente** in modo da ottenere un formato unico.

- La **seconda richiesta** riguarda l'estrazione delle informazioni sugli **ordini** e, come nella prima richiesta, la loro uniforme strutturazione.

- La **terza richiesta** si attiva quando il cliente accetta l'offerta: si tratta di **far partire automaticamente la conferma dell'ordine**.
> Riguardo a questo punto, purtroppo non ho sufficienti dettagli sul processo di conferma degli ordini che usate per fornirvi una stima di fattibilità precisa. E' un punto da approfondire. Tuttavia, se esistono delle API accessibili esternamente o se il sistema prevede semplicemente l'invio degli ordini confermati via email ad un terzo, non ci dovrebbero essere grosse complicazioni.

## Come immagino l'applicazione



Sarà una applicazione che resterà in ascolto delle email che ricevete e, una volta ricevute, estrarrà le informazioni necessarie per la gestione degli ordini e delle offerte. Verranno quindi strutturate.

Le informazioni strutturate verranno salvate su un database interno e potranno essere visualizzate attraverso una piattaforma web. Questa piattaforma sarà accessibile solo a voi e a chiunque possieda le credenziali.

In una prima versione del progetto, possiamo immaginare che la piattaforma avrà le seguenti 3 pagine:

- **Pagina Dashboard**: una pagina iniziale che mostra un riepilogo della quantità di ordini e offerte ricevuti nell'ultimo mese, settimana o giorno.

- **Pagina Ordini**: una pagina che visualizza una tabella di tutti gli ordini ricevuti e confermati dal cliente, con la possibilità di filtrarli per data, stato, cliente, ecc.
> Facendo focus su una riga specifica della tabella sarà possibile visualizzare un'altra tabella con i dettagli dei materiali dell'ordine già strutturati, come i materiali richiesti, le quantità, i prezzi accordati, ecc.

- **Pagina Offerte**: una pagina che mostra tutte le offerte ricevute dai vari clienti, anch'esse filtrabili per data, stato, cliente, ecc.
> Anche qui, facendo focus su una riga specifica della tabella sarà possibile visualizzare un'altra tabella con i dettagli dei materiali dell'offerta 


---

## Possibili features

La piattaforma potrebbe diventare un vero e proprio gestionale, con la possibilità per ogni riga di ogni tabella di avere delle azioni (conferma ordine,  rispondi al cliente X cosa, rifiuta offerta, ecc ecc...)

- **Ulteriore Automatizzazione**: la possibilità di automatizzare l'invio di email di avvenuta ricezione della richiesta di offerta, del tipo: "Grazie per averci inviato la richiesta riguardante i materiali (e qui si inserisce la tabella già strutturata dei materiali richiesti dal cliente), la stiamo valutando e ti faremo sapere a breve". 

- **Ricerca interna degli ordini passati tramite linguaggio naturale**: un campo di ricerca che permette di cercare ordini passati in base a una query in linguaggio naturale. Ad esempio, scrivendo "Mostra tutti gli ordini di marzo 2024" verranno visualizzati tutti gli ordini ricevuti nel mese di marzo 2024 all'interno di una tabella. Oppure qualcosa di più complesso come "Mostra tutti gli ordini che contengono TUBI LAM di lunghezza 155mm".

---
### Note poco interessanti

- Il tipo di struttura dei dati la possiamo scegliere e cambiare insieme nel tempo in modo che siano già conforme ad altre operazioni esterne

- Il collegamento della vostra casella email con l'applicazione sarà possibile all'interno della piattaforma web attraverso un semplice Oauth2 senza la necessità di inserire le credenziali o altri dati sensibili del vostro account email. 
> Nota: Le credenziali della piattaforma web e quelle del vostro account email non sono correlate

- Devo ancora capire come gestire i dati delle email in arrivo, in quanto tenerle su un database potrebbe violare il gdpr. Potrebbe essere obbligatorio dare una scadenza alle informazioni ricevute e cancellarle automaticamente dopo un certo periodo di tempo.

- All'interno della piattaforma potrete collegare più caselle email all'applicazione se necessario, e gestire tutte le email di ordine/offerta in entrata in modo unificato.





