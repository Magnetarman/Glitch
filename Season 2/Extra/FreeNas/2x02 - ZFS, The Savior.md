# ZFS, The Savior

**RAID IS NOT A BACKUP**

## Affidabilità dei dati
- Ad oggi si pone sempre meno attenzione a come i moderni sistemi operativi e i file system trattano alla radice i dati. Dopo uno studio durato 6 mesi posso dire sinteticamente che *li gestiscono davvero male*.
- Un dato infatti se non viene correttamente trattato dal file system, da sistema operativo, dalla Ram in cui viene immagazzinato col tempo può corrompersi parzialmente creando problemi più o meno gravi.
- Risvolti tecnici sul recupero dati.
- Avete perso i dati per una errata formattazione o rimozione di partizione ?, L’HD si è danneggiato ? Quali sono i migliori FS per poter recuperare tutti i vostri dati ?
- Se avete rimosso l’intera partizione o formattato l’intero disco, di fatto, sono solo state cancellate poche informazioni. Infatti tutti i dati, sono ancora nello stesso posto e non vengono cancellati, a meno che non abbiate fatto una formattazione ‘lenta’ o ‘sicura’, che scrive tutti i settori, ma che in genere non si fa mai in quanto richiederebbe molte ore in caso di HD capienti. Nel caso fosse stato realizzato con una partizione Microsoft (FAT/NTFS), il recupero è pressoché totale. Con software anche di bassissimo costo ed addirittura alcuni free, è possibile ricostruire l’intera struttura e recuperare tutti i files. Il recupero infatti non è semantico, ma RAW. Non importa che tipo di file sia, lui lo recupera as is, perchè riesce ricostruire tutta la FAT (File Allocation Table) sfruttando i collegamenti che sono presenti prima e dopo i vari chunk che vengono trovati.
- La procedura richiede diverso tempo, ma il recupero è garantito.
- Diverso se invece vengono utilizzati altri FS.
- Per esempio su MAC con HFS+ e ancor peggio con APFS, il recupero dati può avvenire solo in modo semantico, pertanto, in base alla completezza dei pattern del software di recupero, si potranno recuperare file di vari formati, più o meno standard. Documenti/Foto ecc ecc. Se il pattern del file che vi serve non è presente nel software di recupero, il vostro file non potrà essere recuperato. (Per linux non so come funziona, non l’ho mai fatto)

**FreeNas** è un sistema operativo open source, scritto principalmente in Python, basato su FreeBSD che tramite diverse tecnologie, a partire dal file system OpenZetaFileSystem (Fork Open Source del File System di classe Enterprise ZFS ideato e sviluppato fino al 2006 dalla Sun Microsystem)

**ZFS è un file system a 128 bit**: può quindi fornire uno spazio di 16 miliardi di miliardi di volte la capacità dei file system a 64 bit (Come NTFS di Windows o HFS+/APFS di Apple). I limiti del ZFS sono concepiti per essere così ampi da non essere mai raggiunti in una qualunque operazione pratica. Bonwick ha affermato che "per riempire un file system a 128 bit non sarebbero bastati tutti i dischi della terra".
 
Alcuni dei limiti teorici del Zettabyte File System (ZFS):
248 — numero di snapshot (3 × 1014);
248 — numero di file (3 × 1014);
16 exabyte — dimensione massima di un file system;
16 exabyte — dimensione massima di un file singolo;
16 exabyte — dimensione massima di un attributo;
3 × 1023 petabyte — dimensione massima di uno zpool;
256 — numero di attributi di un file (attualmente limitato a 248);
256 — numero di file in una directory (attualmente limitato a 248);
264 — numero di device per ogni zpool;
264 — numero di zpools;
264 — numero di file system in uno zpool.
Un utente che volesse creare mille file al secondo, impiegherebbe 9000 anni a raggiungere il limite. La cosa bella è che OpenFS può facilmente essere aggiornato, per questo si parla di limiti teorici ed è retrocompatibile con le precedenti versioni in lettura e scrittura per cui risulta relativamente facile accedere ai dati storati con questo file system anche a distanza di anni.
 
Anche Apple nel suo nuovo File System denominato APFS ha integrato alcune tecnologie derivate da ZFS come lo Snapshot e lo spostamento sicuro dei file.
 
Per avere una minima idea di quanto sia uno ZettaByte secondo alcuni studi rilasciati da Google, il tuo intero impianto server, inclusi Google Drive, i dati del motore di ricerca, di Gmail e di Youtube arrivano a generare una mole di dati intorno ai 1,2 - 1,4 Zettabyte di dati per cui un FileSystem bello potente.

## Perchè il Backup è fondamentale ?

- Una strategia poco funzionale, con la mole di dati di oggi rischia di farci perdere, se non correttamente utilizzata dei ricordi importanti per noi
- Il concetto di centralizzazione dei dati. Ovvero utilizzare preferibilmente che tratti tutti i tipi di dati in quanto al giorno d’oggi oltre le foto, produciamo tantissimi tipi diversi di dati che possono essere fondamentali per noi e per la nostra famiglia oltre ai classici contenuti Audio/Video.
- Utilizzare il computer come sola unità di elaborazione ed cercare di abbandonare il concetto di avere tutti i dati salvati su pc, tablet, telefoni che spesso a causa degli stress a cui vengono sottoposti aumentano considerevolmente la possibilità di perdita di dati.
- Rischi Cryptolocker

## Il Cloud è davvero una buona strategia ?

- Attualmente con la mole di dati prodotta, le connessione non troppo affidabili che abbiamo oggi in italia ed l’aggiornamento continuo dei dati che facciamo rendono spesso il cloud impraticabile
- Se il servizio decide di vendere i tuoi dati oppure di chiudere potresti avere gravi problemi a tirare giù moli elevate di dati prima dello ShutDown
- Le app o i servizi Cloud per risparmiare spesso o per dare l’idea di sembrare più intelligenti spesso combinano dei veri disastri durante la sincronizzazione dei dati
- Siamo sicuri che i dati dopo un Tot di tempo siano davvero leggibili al 100% sui “Sicuri” servizi Cloud, che seppur minimo hanno comunque un tasso di fallimento elevato se rapportato a quanti dati devono gestire ?
- Se sei senza connessione internet e devi necessariamente lavorare a qualche progetto che hai sul cloud ?
    -Il cloud è sempre da scegliere come backup di secondo o terzo livello, la dove possediate una infrastruttura in grado di supportarla e di disponibilità finanziarie per ottenerlo, che dipende anche dalla quantità di dati che avete da preservare. Sebbene da considerarsi come ‘ulteriore’ backup, c’è sempre da tenere conto, che il cloud ben fatto, è comunque una soluzione, spesso immune ai vari cryptolocker e consente di poter usufruire dei vostri dati ovunque siate nel pianeta. Va sempre tenuto conto che potrebbero essere dati che da un momento all’altro potrebbero scomparire,  o per deficit tecnici, o per chiusura dei servizi. Ma in generale questioni gestibili nei tempi. Oggi i costi di alcuni servizi sono piuttosto interessanti, e se si è nelle condizioni è una cosa che come aggiunta ad un solido backup, può essere considerata.

