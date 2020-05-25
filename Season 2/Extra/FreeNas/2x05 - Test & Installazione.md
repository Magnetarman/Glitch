# 2x05 - "Test & Installazione"

Dopo aver montanto i pezzi principali del vostro Server (tutto tranne i dischi) conviene iniziare una serie di test per controllare con una buona percentuale di aver ricevuto Hardware che non presente problemi di fabbrica e non ritrovarsi come il sottoscritto con la scheda madre del server col controller SAS non funzionante.

- Controllare dal Bios le temperature del processore a riposo per controllare che la dissipazione sia sufficiente, ovviamente se avete utilizzato i dissipatori consigliati dovreste mantenere anche sotto sforzo delle temperature non superiori ai 60° anche d'estate per cui un ottimo modo per far durare a lungo la CPU
- Eseguire sui banchi di Ram un memtest di almeno 6 - 8 ore per controllare eventuali difetti.
  - Scaricare il Tool, disponibile sia per Windows che per Mac [Link](https://www.memtest86.com/download.htm)
  - Generare una penna bootabile con l'immagine che avete scaricato
  - Far partire il vostro server selezionando la penna come disco di Boot
  - Andare a dormire e controllare la mattina successiva se il software sta girando senza errori rilevati
- Eseguire un Test sui dischi acquistati per rilevare eventuali settori corrotti oppure una meccanica danneggiata dal trasporto
  - Scaricare l'ottimo Tool di Western Digital per effettuare i test anche se i dischi sono di marca differente [Link](https://support.wdc.com/downloads.aspx?p=3&lang=en) ed eseguire un test approfondito su ogni disco acquistato in modo da controllare se ci siano eventuali errori.
  - Il test impiegherà molto tempo per ogni singolo disco per cui se avete un vecchio computer a cui collegare i dischi da prendere in esame considerate quella come postazioni di test in quanto il Tool della WD supporta anche Windows XP e non richiede un processore potente per effettuare i Test.
  - In alternativo potete utilizzare il server stesso installando su un SSD oppure un vecchio disco rigido temporaneamente Windows 10 (anche non in possesso di una licenza) oppure Windows XP in modo da poter installare sul server il software della WD e fare i test da lì, in modo da testare per bene anche i cavi SATA e di alimentazione in modo da escludere qualsiasi problema di natura Hardware.
  - Posizionare il server in un luogo con un buon ricircolo d'aria e possibilmente nell'area utile di un condizionatore d'aria e lontano il più possibile da termosifoni ed altri fonti di calore, in modo da tenere il più bassa possibile la temperatura durante tutto l'anno.

## Installazione

Installare FreeNas è una procedura relativamente semplice. Infatti dopo aver collegato i dischi che utilizzeremo per ospitare i nostri dati, aver collegato i dischi su cui verrà ospitato il sistema operativo e collegata la Penna USB creata, seguire la procedura prestando attenzione ad installare il sistema nel disco corretto.

Al termine della procedura bisognerà inseire la password dell'account Root, da cui procederemo ad effettuare tutte operazioni. Si consiglia di utlizzare una password abbastanza complessa ma facile da ricordare in quanto la si dovrà inserire ad ogni Login tramite interfaccia Web ed se il nostro server rimarrà in rete locale non esponendosi in alcun modo sulla rete non ci saranno problemi ad utilizzare una password più semplice del solito.

Riavviato il server e tolta la chiavetta di installazione, per controllare lo stato della macchina possiamo procedere in 2 modi :

- Utilizzare Monitor + Tastiera

- Utilizzare il controllo remoto IPMI (Sconsigliato in questa fase)

- Attendere il caricamento del sistema

- Segnarsi L'ip di uscita della dashboard

- Collegarsi ed inziare la configurazione di FreeNas
  
  - Creazione del o dei Pool
  - Creazione degli utenti e gruppi
  - Applicazione delle preferenze

## Installazione - Fase 2

- Creazione dei dataset
- Creazione degli endpoint
- Installazione dei plugin necessari
- Configurazione dei vari plugin
- Avvio dei servizi necessari
- Creazione degli shares
