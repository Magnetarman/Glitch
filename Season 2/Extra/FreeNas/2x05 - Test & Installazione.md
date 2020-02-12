# 2x05 - "Test & Installazione"

Dopo aver montanto i pezzi principali del vostro Server (tutto tranne i dischi) conviene iniziare una serie di test per controllare con una buona percentuale di aver ricevuto Hardware che non presente problemi di fabbrica e non ritrovarsi come il sottoscritto con la scheda madre del server col controller SAS non funzionante.

- Controllare dal Bios le temperature del processore a riposo per controllare che la dissipazione sia sufficiente, ovviamente se avete utilizzato i dissipatori consigliati dovreste mantenere anche sotto sforzo delle temperature non superiori ai 60° anche d'estate per cui un ottimo modo per far durare a lungo la CPU
- Eseguire sui banchi di Ram un memtest di almeno 6 - 8 ore per controllare eventuali difetti.
  - Scaricare il Tool, disponibile sia per Windows che per Mac [Link](https://www.memtest86.com/download.htm)
  - Generare una penna bootabile con l'immagine che avete scaricato
  - Far partire il vostro server selezionando la penna come disco di Boot
  - Andare a dormire e controllare la mattina successiva se il software sta girando senza errori rilevati
- Eseguire un Test sui dischi acquistati per rilevare eventuali settori corrotti oppure una meccanica danneggiata dal trasporto
    - Scaricare l'ottimo Tool di Western Digital per effettuare i test anche se i dischi sono di marca differente [Link](https://support.wdc.com/downloads.aspx?p=3&lang=en) ed eseguire un test approfondito su ogni disco acquistato in modo da controllare se ci siano eventuali errori
    - Il test impiegherà molto tempo per ogni singolo disco per cui se avete un vecchio computer a cui collegare i dischi da prendere in esame considerate quella come postazioni di test in quanto il Tool della WD supporta anche Windows XP e non richiede un processore potente per effettuare i Test
    - In alternativo potete utilizzare il server stesso installando su un SSD oppure un vecchio disco rigido temporaneamente Windows 10 (anche non in possesso di una licenza) oppure Windows XP in modo da poter installare sul server il software della WD e fare i test da lì, in modo da testare per bene anche i cavi SATA e di alimentazione in modo da escludere qualsiasi problema di natura Hardware 
