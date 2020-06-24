# [X] Metallo

Per costruire il vostro primo server oltre ai concetti espressi nella premessa conviene preventivamente studiare in maniera analitica quati dati vorrete stoccare all'interno del sistema.

In basso inserisco come esempio da seguire, calcolatrice alla mano del mio server definitivo.

## FreeNas Disk Partition (Storinator 30 - WD 8TB) - **Hyperion**

## Software - 4 Disk (Raidz1) [14 TB Usable Safe]

    Windows = 70% (Prod Plugin Included)
        > 9.8TB Max
    Mac = 30%  
        > 4.2TB Max

## Work - 10 Disk (Raidz3) [33 TB Usable Safe]

    WebDesign = 10% (Site Backup + Flywheel Backup)
        > 3.3TB Max
    AudioProd = 30% (No Plugin) [MixDown Folder Cloud Sync]
        > 9.9TB Max
    Foto = 25%
        > 8.25TB Max
    VideoProd = 30%
        > 9.9TB Max
    Documenti = 5% (All Documents) [Cloud Sync]
        > 1.65TB Max

## Media - 10 Disk (Raidz3) [33 TB Usable Safe]

    Media = 80%
        > 26.4TB Max
    Jail = 20%  (Plex, Gitlab, Transmission)
        > 6.6TB Max

## Torrent - 2 Disk (Mirror) [5TB Usable Safe]

    Torrent = 100% (Incomplete + To Watch)
        > 5TB Max

## Games - 4 Disk (Raidz1) [14TB Usable Safe]

    Platform = 80%
        > 11.2TB Max
    ISO = 20%
        > 2.8TB Max

Ovviamente lo Spazio è solo una delle problematiche che dovremmo affrontare quando andremo a costruire un server domestico. La mia idea, come notate dal titolo è quella di prendere un server chiamato [Storinator](https://www.45drives.com/products/storage/) costruito dall'azienda americana 45Drives, dietro anche alla piattaforma Cloud [Blackblaze](https://www.backblaze.com/), dove una miriade di problematiche relative alla corretta gestione del server vengono ampiamente risolte By Design direttamente dal costruttore. Ma andiamo ad analizzarle meglio:

- FreeNas viene installato su un disco di piccole dimensioni, solitamente una Sitck USB oppure una SSD di piccole dimensioni (8GB - 120GB MAX) in quanto il sistema in se occupa veramente poco spazio ed è completamente diviso dagli HDD che andranno poi ad ospitare i nostri dati. Inoltre le unità adibite all'installazione del sistema verranno poco sollecitate da letture e scritture in quanto una volta che il sistema ha effettuato il Boot viene completamente caricato in RAM ed opera per il 90% lì. Ovviamente conviene creare un mirror del disco di Boot utilizzando due unità identiche in modo da ridurre la corruzione o la perdita dei dati che pur non essendo critica (i dati importanti sono sugli HDD e possono facilmente essere letti e reimportati anche su sistemi FreeNas differenti, a patto di non essere stati protetti con password prevalentemente.) ci spingirebbe ad effettuare tutta la configurazione del sistema da 0, creando non poche noie negli ambienti più complessi. Comunque periodicamente conviene scaricare un backup della configurazione offline e caricarla su di un nostro Cloud. Essendo del peso di pochi MB è facile da conservare in un luogo relativamente sicuro e su supporti differenti dal nostro server. Salvando la configurazione completa, che il sistema ti fa generare ad ogni aggiornamento vengono inluse anche le eventuali password utilizzate e le chiavi di criptazione adottate per proteggere il contenuto dei dischi. Infatti se qualcosa dovesse andare storto, sia sullo stesso sitema che su un sistema secondario di backup, caricando quei file il sistema potrà leggere senza problemi anche il contenuto protetto dei dischi senza alcuna difficoltà.

- Da una analisi più approfondita emerge che per quanto riguarda True Nas Core e quindi con l'aggiunta ufficiale del supporto alla piattaforma di AMD è possibile ridurre considerevolmente il costo del nostro server a parità di performance in quanto AMD su tutti i suoi processori mantiene attivo il supporto alle memorie ECC

- [X]Processori
  
  - Intel i3-9100f 4Core [Link Amazon](https://amzn.to/3aOFgFc)
  - Intel Xeon E5-2603 V4 6Core [Link Amazon](https://amzn.to/2TOMgfb)
  - AMD Ryzen 2600 [Link Amazon](https://amzn.to/2X0QXUn)
  - AMD Athlon 200GE [Link Amazon](https://amzn.to/2ZB7Czs)

- [X]Dischi
  
  - WD 3TB Red [Link Amazon](https://amzn.to/2Y8bZRZ)
  - Seagate IronWolf 4TB [Link Amazon](https://amzn.to/3cQcCDC)
  - Seagate IronWolf 8TB [Link Amazon](https://amzn.to/3bHZwrR)
  - WD 6TB Red [Link Amazon](https://amzn.to/38EWenE)
  - WD 8TB Red [Link Amazon](https://amzn.to/2vjBTWs)
  - HGST 6TB [Link Amazon](https://amzn.to/2NU9YD1)
  - Sandisk Penna USB 16GB [Link Amazon](https://amzn.to/2RlvkuZ)

- [X]Ram (Possibilmente Ecc) [X]
  
  - 8GB ECC [Link Amazon](https://amzn.to/2Ggq05V)

- [X]Case
  
  - Cooler Master N300 [Link Amazon](https://amzn.to/2ObBc8n)
  - Supermicro CSE-721TQ-250B [Link Amazon](https://amzn.to/2yWH3Kd)

- [X]Scheda madre (Possibilmente ServerMicro)
  
  - ServerMicro x11SCL-F0 [Documentazione](https://www.supermicro.com/en/products/motherboard/X11SCL-F) - [Link Amazon](https://amzn.to/3aCU7lS)
  - SuperMicro All in One [Link Amazon](https://amzn.to/38CU2Nq)

- [X]Alimentatore
  
  - Seasonic 650W Bronze [Link Amazon](https://amzn.to/2vjW1I2)

- [X]Dissipatore CPU 
  
  - Artic Freezer 34 [Link Amazon](https://amzn.to/2uAasqN)
  - Cooler Master Hyper TX3 [Link Amazon](https://amzn.to/36p1Uk6) 
