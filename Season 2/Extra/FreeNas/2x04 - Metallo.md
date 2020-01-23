# Metallo

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


Ovviamente lo Spazio è solo una delle problematiche che dovremmo affrontare quando andremo a costruire un server domestico. La mia idea, come notate dal titolo è quella di prendere un server chiamato [Storinator ](https://www.45drives.com/products/storage/) costruito dall'azienda americana 45Drives, dietro anche alla piattaforma Cloud [Blackblaze](https://www.backblaze.com/), dove una miriade di problematiche relative alla corretta gestione del server vengono ampiamente risolte By Design direttamente dal costruttore. Ma andiamo ad analizzarle meglio:

- FreeNas viene installato su un disco di piccole dimensioni, solitamente una Sitck USB oppure una SSD di piccole dimensioni (8GB - 120GB MAX) in quanto il sistema in se occupa veramente poco spazio ed è completamente diviso dagli HDD che andranno poi ad ospitare i nostri dati. Inoltre le unità adibite all'installazione del sistema verranno poco sollecitate da letture e scritture in quanto una volta che il sistema ha effettuato il Boot viene completamente caricato in RAM ed opera per il 90% lì. Ovviamente conviene creare un mirror del disco di Boot utilizzando due unità identiche in modo da ridurre la corruzione o la perdita dei dati che pur non essendo critica (i dati importanti sono sugli HDD e possono facilmente essere letti e reimportati anche su sistemi FreeNas differenti, a patto di non essere stati protetti con password prevalentemente.) ci spingirebbe ad effettuare tutta la configurazione del sistema da 0, creando non poche noie negli ambienti più complessi. Comunque periodicamente conviene scaricare un backup della configurazione offline e caricarla su di un nostro Cloud. Essendo del peso di pochi MB è facile da conservare in un luogo relativamente sicuro e su supporti differenti dal nostro server. 


- Processori 
- Dischi
- Ram (Possibilmente Ecc)
- Case arioso
- Scheda madre (Possibilmente ServerMicro)