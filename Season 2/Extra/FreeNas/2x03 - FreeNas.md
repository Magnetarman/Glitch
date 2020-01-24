# FreeNas, La Soluzione Definitiva

- L’utilizzo di HD predisposti (WD Serie Rossa, HGST) e di Ram ECC (Crucial Preferibile, oppure Kingston) sono consigliati da FreeNas per assicurare insieme a ZFS un’affidabilità vicina al 100% del dato storato nel tempo.

- FreeNas consiglia di utilizzare il suo motore interno di RAID Software invece di avere RAID Hardware in quanto avendo avendo meno layer possibili può assicurare di risolvere facilmente possibili errori e problemi causati durante la conservazione dei dati all’interno del sistema.

- FreeNas gestisce anche, tramite iocage (Sistema nuovo di Jail), dalla versione 11.2 i plugin abbandonando il precedente sistema Warden che aveva alcuni problemi prestazionali e poteva causare delle privilege escalation se non correttamente configurato.  Dalla versione **11.2 - U7** uscita nell'ultima parte del 2019 tra i Fix ha attivato anche la possibilità di aggiornare le Jail tramite un comodo bottone, non funzionante a causa di un bug nelle precedenti release.

- Tutta questa potenza infine può essere gestita sia da riga di comando per i più smanettoni che da una comodissima interfaccia web che se prima era un buon compromesso ma molto vetusta dal lato design, nelle ultime versione sta venendo gradualmente riscritta in angular e potenziata con diverse funzioni come il potenziamento del servizio rsync per supportare anche push o pull di dati dai maggiori servizi di Cloud Storage.

- I diversi Plugin installabili con un click automaticamente da FreeNas permettono inoltre di storare correttamente dei dati anche di manipolarli ed usufruirne in diversi modi.

- Classico esempio è il Plugin di Plex per i file Video/Audio. Oppure Gitlab in versione Community (Open Source) per gli sviluppatori che vogliono avere la piena padronanza dei loro progetti sviluppati e gestiti attraverso il sistema di versioning Git.

- Tenere il dati al sicuro nel tempo tramite il processo di **Scrub**.

- Come Funziona Freenas
  - Cosa sono le Vdevs
  - Diversi tipi di RAID Software
    - Stripe
    - Mirror
    - RAIDz1, RAIDz2, RAIDz3

Una volta creata la struttura dei dischi preferita chiamata Pool oppure col nome che preferite, bastera andare nella schermata di FreeNas che viene interamente gestito da una schermata via Browser, come tutti i NAS nella sezione **Pools** e da li, creare i diversi dataset dove andare ad inserire i dati.

EX - Un dataset chiamato *Documenti* per tutti i documenti, un altro magari chiamato *Media* dove inserire in sotto cartelle le varie foto, film ecc. Inoltre vi ricordo che potente inserire nel campo delle descrizioni una breve descrizione del dataset in modo che anche se lo chiamate in modo criptico riuscirete facilmente ad identificare l'utilizzo finale. Sotto ecco [l'immagine](https://github.com/Magnetarman/Glitch/blob/master/Season%202/Extra/FreeNas/Foto/Pools.jpg) del mio set, ma è a solo scopo informativo.

**Attenzione** - Per una corretta configurazione si consiglia nelle impostazioni di creazione del dataset di assegnargli una quota in GB o TB finita di spazio, che può essere sempre variata con un click. infine si consiglia di non assegnare mai più del 70% - 80%
 dello spazio totale del server in modo da avere sempre le performance massime.

Infatti ZFS inizia ad avere importanti cali di perfomance e di gestione dei dati se vengono superate quelle soglie, creando inutili grattacapi. Bloccando così la dimensione massima occupabile dai diversi dataset quando raggiungeremo la quota massima avremo comunque il 100% delle performance in lettura / scrittura del server e potremmo facilmente cancellare dati non più utili oppure semplicemente procedere all'espansione della capacita dei dischi del server.

Una volta creati i diversi Dataset per renderli visibili in rete e navigabili da Explorer o dal Finder di MacOS bisogna spostarsi nella sezione "Sharing" e da li creare e nominare i vari punti.

Potrebbe risultare complicato per i neofiti ma basta inserire il percorso */mnt/NomedelPool/Endpoint* e lasciare le impostazioni di Default.

## FreeNas Vs. TrueNas

True Nas è sostanzialmente la versione a pagamento di FreeNas. infatti questa versione viene ceduta solo con i server venduti direttamente dalla IXSystems. E' praticamente identica alla versione Free e si discosta per il supporto alle Jail ed alle macchine virtuali assente pre questioni di stabilità e sopratutto in relazione al fatto che la versione a pagamento di FreeNas viene utilizzata sopratutto per lo storage massivo di dati in ambito aziendale e quindi la manipolazione degli stessi per merito dei Plugin non viene per nulla considerata.

Oltre a questa differenza sostanziale ha anche una schedule completamente diversa per quanto riguarda gli aggiornamenti. Infatti mentre FreeNas ha di solito un aggiornamento ogni 6 mesi, TrueNas ha un aggiornamento maggiore ogni anno mentre durante questo tempo viene aggiornato in maniera minore sostanzialmente tramite Bugfix.

Infine tutte le modifiche che arrivano a True Nas sono state precendentemente testate su FreeNas per diverso tempo. Per semplificare ulteriormente il ragionamento FreeNas può considerarsi il ramo Beta/Insider di True Nas, ovviamente questi termini non sono assuluti, in quanto FreeNas dal suo magior Update dalla V 11 in poi, tranne qualche piccolo Bug relativo alla nuova interfaccia proposta basata su Angular non mi ha mai dato nessun tipo di problema di affidabilità.
