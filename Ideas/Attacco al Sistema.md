# "Attacco al Sistema"

- **Data da definire** *ore 18.00*, avevo da poco concluso una riunione preliminare con il mio nuovo cliente, mi aveva contattato per riscrivere da 0 il tema del suo sito di vendita di vestiti online. 
- *Ore 20.30* Installo il plugin di diagnostica per portarmi avanti con il lavoro, vado a cenare. Faceva caldo ed essendo reduce da notti insonni per finire il redesign del sito della galleria, decido di guardare una serie di Netflix ed andare a dormire per poi iniziare a lavorarci seriamente l'indomani.
- *Ore 03.30* il telefono non smette di vibrare, erano arrivate una montagna di email dal tool di diagnostica, accendo lo schermo del telefono che illumina la stanza buia e cerco di capire cosa sta succedendo.
- *Ore 03.32* le email riportano delle notizie catastrofiche. L'intero sito è invaso da codice malevolo, ad aggravare la situazione sono stati registrate decine di tentativi di accesso non riusciti con credenziali varie di amministratore. La situazione è seria, salto giù dal letto cercando di non svegliare mio fratello nella stanza accanto, corro al Pc.
- *Ore 03.35* sono già operativo, mi collego al sito, per fortuna le mie credenziali vanno ancora e noto il sito essere maledettamente lento, forse colpa dell'attacco in corso.
- *Ore 04.20* dopo test vari scopro che il dominio su cui è ospitato, Aruba, ha una decrepita versione di PHP, la versione 5.2 uscita a novembre 2006 e rispetto alla versione 7 piena di falle delle proporzioni del Titanic. A difficoltà forzo il server a fare girare la versione 7, secondo Aruba la più aggiornata, uscita a dicembre 2015, mi faccio forza, sempre meglio di niente.
- *Ore 04.30* le email degli attacchi continuano, inizio a sentirmi sopraffatto, sudo, bestemmio parecchio, non riesco a capire dove sia la falla che sta facendo affondare il mio Titanic. Ad un certo punto, quasi per caso l'occhio cade sulla sezione plugin di WordPress. Ci clicco e noto che quasi tutti i plugin non sono aggiornati, lancio l'aggiornamento.

- *Ore 04.32* l'aggiornamento si inceppa sempre sullo stesso plugin, cerco il nome su Google e noto che oltre ad essere scritto veramente con il culo ed avere tutte recensioni ad una stella ha delle funzioni di personalizzazioni della parte grafica del tema completamente inutili anche a chi sa mettere un minimo le mani e sa come funziona il sistema tema genitore/tema figlio di WordPress. 

- *Ore 04.3*5 faccio l'agghiacciante scoperta il cazzo del plugin installato, che nemmeno faceva un cazzo di buono, essendo a pagamento, 20€, era craccato e quindi aveva all'interno tutta una serie di operazioni di sql injection e attacchi xss per creare dei casini allucinanti a te, al tuo sito, al tuo PC e sopratutto ai visitatori. NDA CHELLA PATANA ... 

- [ ]  Attenzione alla persona scelta per costruire il vostro sito
- [ ]  Se non sapete cosa state facendo, non fate nulla, se il vostro sito vi permette di portare a casa lo stipendio prendete un professionista, al massimo se non potete permettervelo se è una persona intelligente concorderà con voi un piano di rateizzazione della cifra
- [ ]  Report siti allucinanti
- [ ]  Attenzione al servizio di hosting
    - [ ]  Versione di PHP aggiornata per prevenire falle e aumentare le prestazioni
    - [ ]  WordPress spesso dopo la dismissione taglia il supporto ufficiale alle versioni di PHP più vecchie, rinforzando il core, velocizzandolo e risolvendo bug di sicurezza generati da versioni vecchie
    - [ ]  Hosting veloce e che abbia una buona reputazione in modo da risolvere alla base la maggior parte dei problemi che un sito possa avere
- [ ]  Chiedere sempre a qualcuno che il mestiere lo sappia fare, altrimenti si rischiano situazioni gravi, anche penali.
    - [ ]  Basta controllare il suo portfolio lavori, se fa siti che come stile e funzioni sono rimasti al 2009, forse anche lui è rimasto congelato a 10anni fa, il mondo è profondamente cambiato

- Spero che questa prima stagione di glitch sia stata di vostro gradimento e vi abbia magari fatto ragionare un pochino su questo bellissimo mondo che prende il nome di web, ma sopratutto ora che siete più informati sarà più difficile per l'improvvisato di turno riuscire a raggirarvi riempiendovi di tecnicismi, false informazioni e ... Perché no anche qualche plugin craccato...

- Mi raccomando, rimanete sintonizzati perché la seconda stagione di glitch è in lavorazione, grazie ancora tutti dei feedback e del supporto noi ci vediamo in futuro, non troppo remoto