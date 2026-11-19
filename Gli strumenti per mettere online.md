# Gli strumenti per mettere online il tuo sito o la tua app

Il sito o l'app li scrive Claude, parlandoci. Per farli uscire dal tuo computer servono tre strumenti, ognuno con un compito solo. Questa scheda ti dice a cosa serve ognuno, quanto costa e quando ti serve. Non devi ricordarla: quando arrivi al momento di pubblicare, dalla a Claude e ti guida lui.

Prezzi e condizioni sono quelli scritti sui siti ufficiali il 19 novembre 2026. Cambiano spesso: prima di pubblicare qualcosa di importante chiedi a Claude di ricontrollarli.

## Quale ti serve

- **Un sito vetrina** (chi sei, cosa fai, contatti, come il sito del Birrificio): **GitHub + Vercel**. Non ha dati da salvare, quindi il database non serve.
- **Un'app con dei dati** (un mini-CRM, un registro, un gestionale): **GitHub + Vercel + Supabase**.

## GitHub: la cassaforte del codice

**Cosa fa.** Conserva il codice del tuo sito con tutte le sue versioni, come per il tuo vault con GitHub Desktop (il compito della Lezione 4, che oggi vedi dal vivo). Se una modifica rompe qualcosa, si torna alla versione di prima.

**Quanto costa.** Gratis, anche per le copie private.

**L'account.** Se hai fatto il compito della Lezione 4 ce l'hai già. Se no, lo crei da github.com/signup.

**Da sapere.** Il codice del sito è una copia separata dal vault, nella sua cartella (`~/Desktop/_Progetti Sviluppo/nome-del-progetto/`). Tienila **privata**: è il modo più semplice per non mostrare per sbaglio qualcosa che non dovevi.

## Vercel: il codice diventa un link

**Cosa fa.** Prende il codice da GitHub e lo trasforma in un sito che chiunque apre dal browser. Ogni volta che salvi una modifica su GitHub, Vercel la mette online da solo, in un minuto.

**Quanto costa.** C'è un piano gratuito (si chiama Hobby), ma **solo per uso personale o non commerciale**: lo dicono le condizioni di Vercel. Va benissimo per imparare, per provare e per i progetti tuoi. Il sito della tua attività o un'app che usi per lavoro sono un uso commerciale: per quelli Vercel chiede il piano Pro, 20 dollari al mese più IVA. Prima di pubblicare il sito vero chiedi a Claude di verificare le condizioni aggiornate e se ci sono alternative gratuite che permettono l'uso commerciale.

**L'account.** Da vercel.com, con «Continue with GitHub»: entri con il tuo account GitHub, senza creare un'altra password, e Vercel vede subito le tue copie su GitHub.

**Da sapere.** Il link che ti dà Vercel finisce con `.vercel.app`. Se vuoi un indirizzo tuo (per esempio `www.latuaattivita.it`), si collega dalle impostazioni del progetto: chiedi a Claude di guidarti.

## Supabase: dove l'app salva i dati

**Cosa fa.** È il database: il posto dove l'app tiene contatti, clienti, ordini. Pensalo come un foglio Google fatto per le app. Gestisce anche l'accesso con password, se l'app deve essere solo tua o del tuo team.

**Quanto costa.** Il piano gratuito comprende 2 progetti attivi e 500 MB di dati, che per un mini-CRM sono tantissimi. Un progetto gratuito **si mette in pausa dopo una settimana senza uso**: si riattiva dal pannello di Supabase, i dati restano.

**L'account.** Da supabase.com, accedendo con GitHub.

**Da sapere: le regole di accesso.** Ogni tabella di Supabase va protetta con delle regole che dicono chi può leggere e modificare i dati. Senza regole, **chiunque abbia il link della tua app può leggere e cambiare i dati**, compresi quelli dei tuoi clienti. È uno dei primi controlli che fa `/controlla-sicurezza`, insieme a un'altra cosa: se l'app ha l'accesso con password, la registrazione deve essere chiusa, altrimenti chiunque si crea un account ed entra.

## Le chiavi: cosa sono e dove vanno

Per collegare l'app a Supabase (o a un altro servizio) servono delle **chiavi**: codici che danno accesso al servizio. Ce ne sono di due tipi:

- **la chiave pubblica** («publishable» su Supabase; nelle guide più vecchie e a volte da Claude è chiamata «anon»): è fatta apposta per stare nel sito, e da sola non è un problema se le regole di accesso sono a posto;
- **la chiave segreta** («secret» su Supabase): dà pieno accesso ai dati. **Non deve mai finire nel codice del sito né su GitHub.**

Due regole semplici:

1. **Le chiavi non si incollano in chat.** Claude ti dice in quale file o in quale impostazione metterle, e lì le incolli tu.
2. **La chiave pubblica** può stare nel codice del sito. **La chiave segreta** sta solo in un file chiamato `.env` sul computer, che Claude esclude da GitHub, e nelle impostazioni del progetto su Vercel («Environment Variables», con il tipo «Secret», così dopo il salvataggio nessuno può più leggerla), e solo se l'app ha una parte che lavora sul server. Se Claude propone di usare la chiave segreta nella pagina, o di darle un nome che inizia per `NEXT_PUBLIC_` o `VITE_` (quei nomi finiscono nel sito), fermalo e chiedi un'altra strada.

## Il percorso, dall'idea al link

1. **Costruisci sul computer.** Apri Claude nella cartella del progetto, fuori dal vault, e costruisci parlandoci. Guardi il risultato nel browser prima che sia online.
2. **Salva su GitHub.** Con GitHub Desktop aggiungi la cartella del progetto e la pubblichi lasciando la spunta sulla copia privata, come hai fatto per il vault. Se ti blocchi, chiedi a Claude di guidarti.
3. **Pubblica con Vercel.** Importi il progetto da GitHub e ottieni il link.
4. **Se ci sono dati, collega Supabase.** Crei il progetto su Supabase, Claude prepara le tabelle e le regole di accesso, tu metti le chiavi nel file `.env` e nelle impostazioni di Vercel. Poi chiedi a Claude di ripubblicare: su Vercel le chiavi valgono solo dalla pubblicazione successiva.
5. **Controlla prima di condividere.** Lancia `/controlla-sicurezza` prima di dare il link a qualcuno, e ogni volta che aggiungi una funzione che tocca i dati.

Da qui in poi ogni modifica è una richiesta a Claude: lui cambia il codice, tu guardi il risultato, lo salvi su GitHub e Vercel lo mette online.
