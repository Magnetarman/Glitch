# FreeNas, La Soluzione Definitiva ?

- L’utilizzo di HD predisposti (WD Serie Rossa, HGST) e di Ram ECC sono consigliati da FreeNas per assicurare insieme a ZFS un’affidabilità vicina al 100% del dato storato nel tempo.
 
- FreeNas consiglia di utilizzare il suo motore interno di RAID Software invece di avere RAID Hardware in quanto avendo avendo meno layer possibili può assicurare di risolvere facilmente possibili errori e problemi causati durante la conservazione dei dati all’interno del sistema.

- FreeNas gestisce anche, tramite iocage (Sistema nuovo di Jail), dalla versione 11.2 i plugin abbandonando il precedente sistema Warden che aveva alcuni problemi prestazionali e poteva causare delle privilege escalation se non correttamente configurato.  Dalla versione **11.2 -U7** uscita nell'ultima parte del 2019 tra i Fix ha attivato anche la possibilità di aggiornare le Jail tramite un comodo bottone, non funzionante a causa di un bug nelle precedenti release.

- Tutta questa potenza infine può essere gestita sia da riga di comando per i più smanettoni che da una comodissima interfaccia web che se prima era un buon compromesso ma molto vetusta dal lato design, nelle ultime versione sta venendo gradualmente riscritta in angular e potenziata con diverse funzioni come il potenziamento del servizio rsync per supportare anche push o pull di dati dai maggiori servizi di Cloud Storage.


- I diversi Plugin installabili con un click automaticamente da FreeNas permettono inoltre di storare correttamente dei dati anche di manipolarli ed usufruirne in diversi modi.

- Classico esempio è il Plugin di Plex per i file Video/Audio. Oppure Gitlab in versione Community (Open Source) per gli sviluppatori che vogliono avere la piena padronanza dei loro progetti sviluppati e gestiti attraverso il sistema di versioning Git.

- Tenere il dati al sicuro nel tempo tramite il processo di **Scrub**.
