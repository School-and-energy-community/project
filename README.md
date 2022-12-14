# Schools as Energy Communities
## Campionato Nazionale Siemens 2023
<img src="image/photo.gif" width="150" height="130"> <img src="image/eolico.gif" width="150" height="130">

### Premessa
Inserire riflessioni degli studenti sul tema ambientale - contributo docente di lettere Prof.ssa Lencioni 

### Finalità
Il presente progetto ha come finalità il monitoraggio energetico di edifici scolastici e di edifici in genere al fine di ottenere:
- in fase **preliminare** le informazioni utili per il risparmio energetico e per il dimensionamento di impianti di produzione da energia rinnovabile a servizio di comunità energetiche;
- a **regime** le informazioni dettagliate circa il consumo e l'utilizzo ottimale degli impianti costituenti la comunità energetica.

Il monitoraggio energetico si riferisce sia all'energia **elettrica** sia all'energia **termica** o ad altra forma di energia prodotta o immagazzinata.

Il sistema di monitoraggio utilizza componenti a bassissimo costo di dimensioni ridotte e con alto livello di affidabilità. Alimentati a batteria sono adatti per essere inseriti in qualsiasi impianto in modo non intrusivo e sicuro, ovvero senza la necessità di dover intervenire e/o modificare i circuiti oggetto di monitoraggio.
Tali componenti sono in grado di trasmettere le informazioni senza intermediari web direttamente su Google Sheets per essere elaborati da opportuna interfaccia software.

Attualmente in commercio esistono svariati servizi di monitoraggio piu' o meno intrusivi. Ne citiamo qui uno per tutti offerto gratuitamente da [e-Distribuzione](https://www.e-distribuzione.it/servizi/contatore/le-mie-letture.html) con relativa [App per smartphone](https://play.google.com/store/apps/details?id=com.enel.mobile.edistribuzione&hl=it&gl=US). Cercheremo in seguito di sfruttare al meglio questi dati aggregati nei casi in cui risultano disponibili all'utente. Tuttavia si tratta sempre di servizio di monitoraggio che, anche quando attivabile, non interagisce piu' di tanto con l'impianto. Altri servizi/prodotti anche se piu' "interattivi", sono pensati normalmente per un monitoraggio lacale di **una singola utenza**. Vedremo invece come il progetto **Schools as Energy Communities** sia in grado di gestire/coordinare al meglio i consumi di **un gruppo di utenze** disperse su un territorio, come sono appunto le comunità energetiche, ottimizzando altresì i diversi sistemi di accumulo che utilizzano tecnologie differenti con relativi limiti e vantaggi, quali ad esempio le batterie al litio e le batterie al sale fuso.

Il progetto nasce dall'idea di monitorare i consumi della nostra scuola [IIS Galilei Artiglio](https://www.iisgalileiartiglio.edu.it/) per contribuire inizialmente ad individuare ed eliminare sprechi energetici e successivamente per fornire strumenti utili anche all'Amministrazione Pubblica al fine di costituire comunità energetiche di scuole e/o di altre realtà del territorio.

### Peculiarità del progetto
Il presente lavoro si rivolge a tutti, in particolare ai non esperti, utilizzando tecnologie robuste ed affidabili a bassisimo costo e open source come Google Scripts. La parola d'ordine è **semplificare il piu' possibile** rendendo accessibile a chiunque concetti e pratiche che spesso sono per addetti ai lavori. Pensiamo che ognuno debba essere e sentirsi protagonista in questa sfida importante a favore dell'ambiente e che le abilità e le competenze dell'esperto non debbano apparire come un sapere inaccessibile ma un "bene comune" da condividere. In altre parole chiunque abbia uno smartphone e ovunque si trovi è in grado di *addestrare* il sistema di monitoraggio, di leggere i consumi energetici e di interagire con i carichi mediante il PLC Siemens. Se poi in alternativa allo smartphone può indossare un paio di occhiali per la **realtà aumentata** tipo [Google Glass](https://www.google.com/glass/start/), allora può sfruttare appieno le potenzialità del sistema sviluppato, come descritto piu' avanti. Il progetto infatti sfrutta l'interfaccia di Google Sheets per consentire all'utente di **personalizzare** in modo semplice ma potente le proprie richieste.

<img src="image/sheets.gif" width="150" height="130">

Di seguito, oltre al video istituzionale del Campionato Siemens, saranno proposti dei video-tutorial esplicativi sull'addestramento e sull'utilizzo del sistema di monitoraggio.

### Semplificare la parola d'ordine ma ... senza banalizzare !
In passato l'energia elettrica è sempre stata intesa come un **servizio**. Oggi abbiamo compreso che in realtà è un **bene prezioso** da gestire attentamente. La sfida quindi è sfruttare al meglio l'energia, riducendone innanzitutto gli sprechi e consumandola quando è disponibile ed a prezzi vantaggiosi per l'utente. Questa affermazione ovvia, ma di non semplice attuazione, assume un peso maggiore di fronte a comunità energetiche dove la domanda e l'offerta da energia rinnovabile risponde a dinamiche proprie di ciascuna singola realtà costituente la comunità stessa. Tuttavia pensando per esempio alle scuole o ad altre strutture pubbliche affini, sarebbe importante capire a priori i consumi energetici specifici. Ad esempio osservando i consumi necessari all'illuminazione artificiale di due o piu' scuole, si potrebbero confrontare i watt per mq assorbiti per aula a parità di efficienza luminosa tenendo conto ovviamente anche dell'illuminazione naturale. Oppure si potrebbero paragonare i consumi termici di edifici costruiti negli stessi periodi, ovvero con involucri edili simili, per capire quali azioni possono essere intraprese per allineare il piu' possibile i consumi a standard comuni. Per far questo occorre allestire una campagna di monitoraggio che utilizzi una tecnologia di facile installazione, "leggera" ed a basso costo, limitando al minimo essenziale i punti di misura. Inoltre il sistema di monitoraggio deve essere flessibile, cioè in grado di poter utilizzare diverse tipologie di sensori per la misura di svariati parametri fisici (temperatura, luminosità, umidità, corrente, tensione, cosfi, ecc). Vedremo poi come il feedback del monitoraggio abbinato ad un **PLC Siemens S7 1x00** diventi un punto di forza irrinunciabile da un punto di vista operativo per un reale e concreto risparmio energetico (ai fini del progetto può essere utilizzata indifferentemente la serie 1200 o la serie 1500).

### Realtà aumentata ###
I componenti scelti nel progetto per il monitoraggio "low cost" sono costituiti da microprocessori ESP32 programmati in microPython in grado di scrivere direttamente i valori delle grandezze fisiche d'interesse in tempo reale su [Google Sheets](https://www.google.it/intl/it/sheets/about/) senza intermediari Web. 
Di seguito si riporta lo schema che prevede una espansione per l'acquisizione di quattro segnali analogici utilizzati per la lettura dei consumi elettrici compreso il cosfì e lo schema con un modulo completo di PT100 "pronto all'uso" per la misura delle temperature di mandata e ritorno delle tubazioni di riscaldamento.
Naturalmente gli scenari che si possono costruire sono molteplici. In rete si trovano svariate librerie in microPython che permettono di sfruttare al meglio le caratteristiche di ESP32. Ad esempio cliccando su [questo link](https://awesome-micropython.com/) si possono trovare diversi progetti interessanti.
Tuttavia ci teniamo a precisare che il progetto ***Schools as Energy Communities*** non è frutto di un mero "copia & incolla", ma al contrario le librerie utilizzate sono state sviluppate ad hoc dal gruppo di lavoro dell'IIS Galilei Artiglio al fine di ottenere un risultato unico nel suo genere.
Da notare che gli ESP32 sono alimentati a batteria e quindi sono indipendenti dal resto dell'impianto oggetto di monitoraggio e che lo stato di carica della batteria al litio è anch'esso registrato in una casella di spreadsheet il cui valore, se al di sotto di una soglia stabilita, può essere comunicato al manutentore via e-mail o es WA grazie al servizio [Google Apps Script](https://www.google.com/script/start/) per la sostituzione/ricarica. 

**Schema con espansione analogica per la misura delle GRANDEZZE ELETTRICHE**

<img src="image/schemata.png" width="450" height="250"> <img src="image/TA.png" width="150" height="90">

**Schema con modulo PT100 per la misura di TEMPERATURA**

<img src="image/schemapt100.png" width="450" height="250">

Nel progetto ***Schools as Energy Communities***, qualsiasi sia la grandezza fisica misurata, questa è facilmente accessibile attraverso la **realtà aumentata**.  
Infatti, per migliorare la percezione da parte dell'utente dei consumi, si è pensato di sfruttare una tecnologia che in futuro sarà sempre piu' presente nei processi tecnologici. Tuttavia la sfida è stata quella di poter applicare con facilità la realtà aumentata anche in contesti piu' generici come quelli di edifici esistenti non tecnologicamente avanzati. Nel caso ad esempio di impianti elettrici e termici solitamente vetusti a servizio delle scuole, si vuole offrire la possibilità al tecnico e/o al manutentore dell'Amministrazione Provinciale o Comunale, di avere l'andamento dei consumi osservando semplicemente il quadro elettrico o la centrale termica oggetto d'indagine.
Per far questo occorre indossare degli occhiali tipo [Google Glass](https://www.google.com/glass/start/) (in alternativa si può utilizzare uno smartphone o un tablet qualsiasi) ed inquadrare il QR Code posto sul quadro elettrico o sull'utenza. Per la lettura del QR Code il progetto prevede l'utilizzo di [Google Lens](https://play.google.com/store/apps/details?id=com.google.ar.lens&hl=it&gl=US&pli=1).
Di seguito si riporta un QR Code per il lettore in modo da poter testare il funzionamento del sistema appena descritto: basta semplicemente inquadrare l'immagine sottostante anche attraverso uno smarphone per aprire la pagina "Graphs" di Google Sheets

<img src="image/qrcode.png" width="200" height="200">

Non è argomento di questo lavoro la cura dell'interfaccia grafica dei fogli se non nella misura funzionale e comprensibile per il raggiungimento delle finalità citate. Tuttavia si ricordano le diverse possibilità di creazione di interfacce utente attraverso le [Class Ui](https://developers.google.com/apps-script/reference/base/ui) di Google App Scripts nonchè attraverso l'installazione di componenti aggiuntivi dal menu *Estensioni*

### PLC S7 1x00: il vero punto di forza ###
Abbiamo visto l'importanza del monitoraggio condiviso su cloud e della reperibilità delle informazioni mediante QR Code. Adesso si tratta di renderle operative sfruttando il web server del PLC Siemens. Il gruppo di lavoro del Galilei Artiglio ha realizzato un file Javascript in grado di leggere i contenuti delle celle desiderate e di passare i valori alle variabili del PLC. In questo modo il cerchio si chiude, nel senso che gli algoritmi impostati su foglio Sheet possono interagire con le uscite dell' S7 1x00 per la gestione dei carichi d'interesse. 

Soffermiamoci un attimo su questo passaggio: <span style="color:blue">le misure energetiche di diversi impianti dispersi sul territorio, sono raccolte all'interno di un foglio di calcolo presente nel Cloud ed accessibile online da piu' utenti secondo restrizioni impostate. Le celle di detto foglio, valorizzate da specifici algoritmi o da valori impostati dagli stessi utenti, costituiscono l'input per uno o piu' PLC Siemens connessi agli impianti costituenti la comunità energetica. Così un sistema distribuito di edifici attivi-passivi diversi per destinazione ed utilizzo, è gestito in modo integrato come se si trattasse di un unico impianto e dove ogni utente può interagire alla pari con la parte che gli compete. </span>

Vediamo meglio il potenziale di queste tecnologie all'interno di una realtà scolastica. Si è già accennato al fatto che si possono monitorare i carichi specifici, ovvero la potenza assorbita per mq di edificio a seguito dell'illuminazione e del riscaldamento. Adesso con il PLC è possibile intervenire operativamente. Ad esempio per l'illuminazione si può intervenire in quelle aree che presentano in determinate ore una illuminazione naturale piu' che sufficiente in termini di lux, parzializzando o addirittura togliendo l'alimentazione alle lampade al fine di evitare la tipica situazione delle "luci accese anche con il sole". Lo stesso discorso vale per il riscaldamento acceso anche nei giorni di scirocco con le aule a finestre aperte (potremmo chiedere conferma a qualsiasi studente di quante volte durante l'anno capitano nella propria scuola situazioni come queste). Esiste tuttavia un utilizzo piu' spinto che è quello delle "autorizzazioni" al consumo di un bene prezioso come quello dell'energia. 
Pensiamo ad esempio ad una scuola che ha l'ascensore ad uso esclusivo di portatori d'handicap e del personale scolastico. Può accadere che l'ascensore sia utilizzato impropriamente (a volte le chiamate ai piani sono un passatempo durante la ricreazione). Se l'ascensore non è dotato di badge (ma anche se lo fosse non cambia niente), è possibile autorizzarne la chiamata tramite il proprio account scolastico attraverso il QR Code. Così anche l'alimentazione per la fruizione didattica dei laboratori può essere autorizzata dal docente di disciplina secondo il proprio calendario scolastico per il tempo necessario alla lezione.
Vedremo anche l'importanza delle combinazioni di orario per evitare picchi di consumo. Si pensi ad esempio alla sovrapposizione simultanea di piu' laboratori energivori tipo saldatura, misure elettriche con prove su macchine elettriche, grandi aule di informatica, compressori di aule di pneumatica ecc.

In altre parole è possibile individuare porzioni di impianto da attivare con autorizzazione utilizzando semplicemente un account personale. L'attivazione è naturalmente un'azione libera dell'utente che in quel preciso momento però è a conoscenza dell'energia prodotta e consumata dalla comunità energetica. Se ad esempio nell'orario scolastico di un docente sono a disposizione aule alternative dove è possibile svolgere lezioni in quel momento "meno energivore", può darsi che il programma svolto, la necessità di un ripasso o altri validi motivi, possano spingere verso un temporaneo ma "virtuoso" cambio di abitudini.  

Di seguito è data la possibilità al lettore di testare le capacità del file sviluppato dal gruppo di lavoro, in grado di far comunicare il PLC Siemens direttamente con i contenuti di Google Sheets. Per prima cosa inquadrare il QR Code seguente con lo smartphone (si consiglia di utilizzare il menu "Cerca" dell'App [Google Lens](https://play.google.com/store/apps/details?id=com.google.ar.lens&hl=it&gl=US) dopo aver inquadrato il QR Code)


<img src="image/qrcode2.png" width="200" height="200">

Se le cose sono andate a buon fine dovreste trovarvi all'interno di un foglio Sheet dove sono riportati semplicemente dei numeri di colore rosso sotto l'etichetta "Carico 1, Carico 2, ... Carico 6". Inserite dallo smartphone nuovi numeri a piacere facendo attenzione di indicare i decimali con la virgola (i valori numerici si inseriscono in basso a sinistra nel campo fx che appare dopo aver selezionato la cella da modificare).

Aprite con Chrome questo [Link di TEST](https://www.albertodelcarlo.it/see/indextest.html) e dovreste vedere i numeri che avete inserito. Potete cambiarli nuovamente da smartphone e premere il tasto refresh del Browser per l'aggiornamento, oppure attendere il refresh automatico ogni sei secondi.


### Architettura del sistema di monitoraggio
La figura seguente mostra in sintesi le relazioni tra i principali componenti del sistema di monitoraggio low cost ed i PLC S7 1x00 Siemens. Si ribadisce che le informazioni scambiate tra gli ESP32 ed i PLC con i servizi APP Script utilizzati nel progetto, tra cui Google Sheets, avvengono **senza intermediari Web**.
 
<img src="image/see.png" width="550" height="350">


### Tecnica NILM e una possibile alternativa del Galilei Artiglio ###
La caratterizzazione dei consumi elettrici di piu' utilizzatori attraverso un'unica misura a monte dell'impianto è un argomento studiato da tempo. Si possono trovare online diversi [studi accademici](https://scholar.google.it/scholar?q=non+intrusive+load+monitoring+academic&hl=it&as_sdt=0&as_vis=1&oi=scholart) che trattano l'argomento di questa tecnica che prende il nome di [NILM](https://en.wikipedia.org/wiki/Nonintrusive_load_monitoring) che significa *Non intrusive load monitoring*. Nella sostanza, alla base del metodo, c'è lo studio, la ricerca di come poter **disaggregare** il dato numerico della misura. Infatti ad ogni carico elettrico inserito corrisponde un aumento di corrente totale assorbita. La misura a monte quindi è un dato **aggregato** che corrisponde alla somma di tutte le correnti.

<img src="image/prese.gif" width="150" height="130"> <img src="image/misura.gif" width="150" height="130">

Ogni sforzo dunque è nel tentativo di riconoscere, partendo dal risultato finale ovvero la misura, il valore esatto dei vari contributi che lo generano. In pratica è un percorso inverso da come abitualmente lo conosciamo. E' come dire: il numero 10 è la somma di 3+2+5. Sì è vero, ma è anche il risultato della somma 6+4. Quale delle due ipotesi è quella giusta ? Per tentare di dare una risposta la tecnica NILM utilizza reti neurali ad hoc in combinazione al tipo di sensori utilizzati. Normalmente si tratta di sistemi chiusi o proprietari, ciascuno con un proprio grado di affidabilità.

Il progetto dell'[IIS Galilei Artiglio](https://www.iisgalileiartiglio.edu.it/) propone un metodo molto semplice per riconoscere i singoli contributi dei carichi **elettrici** e **termici**. 
Il metodo si basa su una semplice regola di operatività: il software estrae un gruppo di carichi le cui combinazioni generano un valore prossimo a quello misurato con un errore impostato dall'utente. Successivamente l'utente stesso verifica se i carichi indicati sono realmente collegati e nel caso che alcuni non lo fossero li esclude ottendo una nuova combinazione. Di seguito si riporta un esempio con carichi elettrici. 
In pratica il progetto sfrutta il web server del PLC che, leggendo la misura da Google Sheet, è in grado di estrarre un insieme di utenze che soddisfano la prima legge di Kirchhoff i cui assorbimenti sono stati misurati singolarmente intervenendo direttamente sugli interruttori di quadro o, nel caso di presenza di PLC S7 1x00, interagendo direttamente tramite il web server con l'impianto. Il software estrae dall'insieme un ridotto gruppo di carichi che verifica la legge con un margine di errore definito, tenendo conto ovviamente del cosfì di ciascun utilizzatore (somma fasoriale). Il cosfì e la corrente di carico sono forniti dalla misura diretta dell'ESP32 installato sull'impianto. Da sottolineare che è sempre possibile verificare in tempo reale l'effettivo collegamento dei carichi individuati agendo sul quadro o sul PLC. Inoltre è possibile inserire nel campo software il valore di corrente e cosfì effettivi del singolo utilizzatore disinserendo tutti gli altri della combinazione. Di fatto è una sorta di addestramento iniziale che una volta compiuto permette di stabilire un margine di errore sufficientemente piccolo per la combinazione. Se due o piu' carichi hanno *esattamente* lo stesso consumo con eguale fattore di potenza (caso raro ma possibile), il sistema proporrà entrambe le due soluzioni. Questo evidentemente è un limite del modello. Tuttavia l'utente può sempre verificare in situ quali sono i carichi effettivamente inseriti. D'altronde se l'utenza A e l'utenza B assorbono esattamente la stessa corrente con lo stesso cosfì, di fatto, ai fini del monitoraggio, sono "intercambiabili". Tuttavia l'informazione può essere ugualmente utile per capire se uno dei due o tutti e due i carichi possono essere sostituiti con modelli aventi tecnologie piu' efficienti. 

Di seguito si riporta un esempio con cinque utenze. Essendo una simulazione offline del PLC, per avere risultati credibili, si raccomanda il lettore di completare i valori dei campi secondo il criterio della prima legge di Kircchoff. Ovviamente se la **somma fasoriale** non è rispettata il sistema risponderà con un messaggio di alert. Per collegarsi alla simulazione occorre cliccare sul link del web server del PLC Siemens (in caso di impianto reale i campi in bianco della misura totale e del cosfì sono valorizzati dalla misura dell'ESP32). L'errore assoluto deve essere maggiore di zero (non esistono misure senza errori).

<img src="image/plc.png" width="150" height="130"> [Link Web Server PLC Siemens](https://www.albertodelcarlo.it/see/sumcombine.html)

La conoscenza del dato disaggregato, ovvero dell'assorbimento dei singoli carichi, permette di:
- stabilire un eventuale elenco di utenze secondarie da disconnettere in caso di consumo eccessivo rispetto all'accumulo considerato e/o dell'irraggiamento solare;
- conoscere il cosfì del singolo utilizzatore per un eventuale rifasamento;
- conoscere l'effettivo consumo del singolo utilizzatore anche in termini di manutenzione programmata/efficienza nel tempo;
- valorizzare economicamente l'utilizzo delle utenze piu' significative da un punto di vista dei consumi per un impiego piu' oculato;
- valutare economicamente le sostituzioni con utenze che utilizzano tecnologie piu' moderne (es. led, inverter, controllori PID ecc.);
- migliorare/modificare le abitudini di consumo dell'utente grazie anche all'utilizzo combinato con il PLC Siemens S7 1x00.

La "bontà" delle misure della corrente e del cosfì totale può essere eventualmente verificata/allineata alle misure messe a disposizione ogni 15 minuti dal servizio di [e-Distribuzione](https://www.e-distribuzione.it/servizi/contatore/le-mie-letture.html) sottoforma di file csv da importare in Google Sheet. In questo modo il servizio di e-Distribuzione può essere integrato con il sistema di monitoraggio proposto nel presente lavoro. 

Naturalmente anche in questo caso il collegamento al web server del PLC potrebbe avvenire sfruttando occhiali di realtà aumentata recuperando le informazioni da smarphone.
Per chi volesse approfondire l'aspetto matematico del modello proposto nel file JS che tratta la prima legge di Kirchhoff può cliccare [qui](https://www.albertodelcarlo.it/see/dsemplici.html).

### Ottimizzare le abitudini di consumo con il PLC S7 1x00 ###
Apparentemente un sistema energetico efficientato alla tecnica vigente ed in modo sostenibile da un punto di vista economico, non ha ulteriori margini di miglioramento se non nell'ottimizzazione delle abitudini di consumo. In generale però, modificare le proprie abitudini non è mai una cosa facile. Ancor di meno se si tratta di attività quotidiane ritenute "necessarie e irrinunciabili". Il progetto **Schools as Energy Communities** si pone appunto l'obiettivo di facilitare il piu' possibile l'interazione tra l'utente ed i consumi energetici, consigliandolo nelle scelte di risparmio possibili attraverso la ***realtà aumentata con interfaccia vocale***. Abbiamo già visto che in alternativa alla realtà aumentata può essere utilizzato un tablet od uno smartphone. Di seguito vedremo come l'utente può ricevere consigli vocali circa la scelta di scenari possibili di risparmio energetico.

Una volta caratterizzato l'impianto con le misure di assorbimento dei carichi e valorizzate le celle spreadsheet, il sistema è pronto per l'interazione vocale con l'utente attraverso il PLC Siemens S7 1x00. Nella simulazione che segue si è scelto di interagire con tre carichi che rappresentano altrettanti laboratori messi a disposizione nell'orario scolastico di un ipotetico docente libero di scegliere. La simulazione è ovviamente rappresentativa di un insieme piu' vasto di casi. Gli scenari che possono essere raccolti in un foglio Google Sheet sono tanti quanto la fantasia e la capacità dell'[energy manager](https://it.wikipedia.org/wiki/Energy_manager) incaricato dall'Amministrazione Pubblica al conseguimento del risparmio energetico. Ci teniamo a ribadire che gli attori chiamati al risparmio siamo tutti noi: studenti, docenti, personale pubblico di qualsiasi livello, cittadini ... in pratica gli utenti. L'esempio seguente si basa sulla realtà scolastica dell'IIS Galilei Artiglio dove la turnazione degli orari dei docenti di disciplina non consente mai di poter scegliere tra piu' di tre laboratori di indirizzo per mattina.

Nella simulazione il lettore può modificare le potenze generate dall'impianto fotovoltaico e dalle batterie di accumulo. Si tratta naturalmente di uno scenario esemplificativo che però comunica tutta la potenzialità degli strumenti utilizzati. Anche l'interfaccia vocale è uno degli strumenti possibili, sicuramente adatto a tutti e di efficacia comunicativa immediata. Si fa notare che nella misura della potenza totale assorbita non sono presenti i consumi dei laboratori A1, A2 ed A3 che rappresentano la scelta futura dell'utente.

Per accedere al foglio di Google Sheet inquadrare il QR Code.

<img src="image/qrparla1.png" width="180" height="180">

Per collegarsi all'interfaccia vocale cliccare sul link del web server del PLC Siemens. Al solito per un impianto reale tutte le celle sarebbero valorizzate dalle misure in tempo reale degli ESP32. Qui nella simulazione il lettore può modificare soltanto le celle con il bordo rosso ed arancio che riproducono la potenza disponibile accumulata nelle batterie e quella prodotta istantaneamente da fonte rinnovabile.

<img src="image/plc.png" width="150" height="130"> [Link Web Server PLC Siemens](https://www.albertodelcarlo.it/see/speach.html)

L'esempio precedente tratta di laboratori, ma nello stesso modo potrebbero essere fornite indicazioni circa i consumi dei sistemi di illuminazione, ma anche di singoli carichi quali fotocopiatrici, distributori di servizi vari, oppure di impianti di climatizzazione di singoli locali ecc.

#### Video  ####
Video di presentazione del progetto

<img src="image/uc.png" width="220" height="140">


