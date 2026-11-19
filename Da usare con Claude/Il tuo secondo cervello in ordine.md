# Il tuo secondo cervello in ordine

In lezione Alberto, tre mesi dopo, ha trovato le crepe del suo sistema: due decisioni in contrasto, una cartella ferma, un collegamento a un file rinominato, una skill che sbagliava. Le ha sistemate con due comandi, ha corretto la skill alla radice e ha cominciato a mettere da parte quello che vale per tutti i clienti.

Qui fai lo stesso sul tuo secondo cervello. Puoi fare tutti i passi o solo quelli che ti servono, in aula o a casa: lo decidi tu.

## Cosa avrai alla fine

- **Tre skill nuove nel vault**: `/stato-vault`, `/stato-memory` e `/youtube-notes`, da rilanciare quando vuoi.
- **Il vault controllato**: collegamenti, mappe, Inbox, progetti fermi. Sistemato quello che hai deciso tu.
- **La memoria misurata e pulita**: quanto sono pieni istruzioni, appunti di Claude e MEMORY dei progetti, e cosa c'era di vecchio o in contrasto.
- **Una tua skill migliorata**, corretta alla radice dopo un errore.
- **Il tuo knowledge avviato**: i primi cassetti in `_claude/knowledge/`, con una voce vera, e la riga nel `CLAUDE.md` che dice a Claude di usarli.
- **Una nota nelle Risorse**, da un video che hai scelto tu.

## Cosa ti serve prima di partire

- L'app di Claude per computer e il tuo vault, con la cartella della lezione in `0-Inbox/`.
- Non serve un vault pieno. Se è quasi vuoto, o non vuoi toccarlo, i controlli li provi sul **vault di Alberto** (`Vault di prova/` nella cartella della lezione), con dati inventati.
- Per il passo 6, il link di un video YouTube che ti è utile.

## Come si usa

1. Questo file deve stare dentro il tuo vault, in `0-Inbox/`, con il resto della cartella della lezione.
2. Apri nell'app una conversazione nuova nella cartella del vault e scrivi:

> Leggi «Il tuo secondo cervello in ordine» nella cartella della Lezione 5 e guidami.

Puoi fermarti quando vuoi, dicendo «ci fermiamo qui». La volta dopo si riparte dal registro in fondo.

## Se qualcosa non va

- **L'app chiede il permesso di scrivere in `.claude/`**: è normale quando installa le skill. Consenti.
- **Una skill non compare nel menu `/`**: scrivi `/reload-skills`, oppure apri una conversazione nuova.
- **Con `/stato-memory` l'app chiede il permesso di leggere una cartella fuori dal vault**: è la cartella degli appunti di Claude. Scegli **Consenti**, mai l'opzione che blocca per sempre. Se non te la senti, di' a Claude di misurare soltanto.
- **Claude vuole correggere tutto insieme**: digli «una cosa alla volta». Decidi tu il ritmo.

---

## Da qui in giù è per Claude: non devi leggerlo

## Dove sei

Claude aggiorna queste tre righe alla fine di ogni passo, e il registro in fondo al file.

- **Passo attuale**: 1 di 6
- **Su quale vault**: -
- **Note**: -

## Regole

Si aggiungono a quelle del `CLAUDE.md` del vault; se qualcosa è in conflitto, valgono quelle del vault, e lo dici.

1. **Sei la guida, un passo alla volta.** Mai due passi senza la conferma della persona. Una domanda alla volta, con opzioni numerate quando servono.
2. **Annuncia prima di scrivere.** Prima di creare, modificare, spostare o copiare un file dici quale, dove e con cosa, e aspetti il sì. Il registro di questa guida lo aggiorni senza chiedere.
3. **Decide la persona.** Quale decisione vale, cosa archiviare, cosa mettere nel knowledge: tu trovi e proponi, lei sceglie.
4. **La persona fa i gesti della lezione.** Quando un passo dice «scrivi tu», mostra la frase o il comando e aspetta che lo scriva lei: lanciare `/stato-vault` e `/stato-memory` e chiedere la correzione di una skill sono le mosse che deve saper rifare da sola.
5. **Niente letture fuori dal vault.** Unica eccezione: la cartella degli appunti automatici di Claude, con `/stato-memory`, dopo averlo detto alla persona. Dentro il vault leggi solo ciò che serve al passo; non aprire diari personali (`Daily/`) né aree private senza un sì.
6. **Non dare per scontato** che la persona abbia clienti, progetti in corso, skill che sbagliano o il vault su GitHub. Se un passo non si applica, si salta e si scrive nel registro.
7. **I file d'esempio sono inventati** (il vault di Alberto, i suoi cassetti di knowledge): servono a capire, non si copiano nel vault della persona.
8. **Spiega ogni termine nuovo** la prima volta: collegamento, mappa, diario, MEMORY, appunti di Claude, knowledge, skill.
9. **Intoppi.** Se qualcosa non torna, chiedi cosa vede sullo schermo o uno screenshot, poi spiega: cosa è successo, perché, l'unica cosa da fare adesso e la strada alternativa. Due tentativi al massimo con lo stesso errore.
10. **Lascia questo file al suo posto.** Non spostarlo né eliminarlo senza un sì esplicito.

## Come condurre

All'avvio:

1. Di' in quale cartella stai lavorando e controlla che sia il vault (contiene `CLAUDE.md`, `Home.md` e le cartelle da `0-Inbox` a `4-Archives`). Se non lo è, dillo e chiedi alla persona di aprire Claude nella cartella del suo vault. Se un vault non ce l'ha, proponi di provare tutto sul vault di Alberto, lavorando da questa cartella.
2. Trova la cartella della lezione in `0-Inbox/` (contiene `INIZIA QUI.md`, `skill-pronte/` e `Vault di prova/`) e di' come si chiama.
3. Leggi il registro in fondo a questo file. Se ci sono passi già fatti, **riparti dal primo non spuntato**, senza rifare domande già fatte.
4. Mostra il percorso in una riga per passo, e di' che si possono fare tutti o solo alcuni. Chiedi da quale partire; se non sa, dal passo 1.

Dopo ogni passo: spunta la casella con la data (`✅ AAAA-MM-GG`; un passo che non si applica si spunta con «saltato: ...»), aggiorna «Dove sei» e aggiungi una riga in cima al registro con ciò che serve per riprendere. Poi chiedi: «continuiamo con il prossimo passo o ci fermiamo qui?».

## I sei passi

### Passo 1 - Le tre skill e su quale vault

1. **Installa.** Spiega in tre righe le tre skill (`/stato-vault` guarda dove stanno i file, `/stato-memory` cosa c'è scritto e quanto è pieno, `/youtube-notes` porta dentro il sapere da fuori). Proponi di copiare le tre cartelle da `skill-pronte/` della lezione in `.claude/skills/` del vault, e di aggiungere tre righe alla tabella delle procedure del `CLAUDE.md` del vault (se la tabella c'è), con quando si usano. Con il sì, copia e aggiungi. Avvisa prima che l'app chiederà il permesso di scrivere in `.claude/`.
2. **Controlla** che compaiano: chiedi alla persona di scrivere `/` e cercarle nel menu. Se non ci sono, `/reload-skills`.
3. **Su quale vault.** Chiedi: «Facciamo i controlli sul tuo vault o, prima, sul vault di Alberto per vedere come funzionano?». Consiglia il suo vault se ha almeno un progetto con diario e MEMORY; il vault di Alberto se è quasi vuoto o se preferisce vedere prima su dati inventati. Scrivi la scelta in «Dove sei». Sul vault di Alberto i controlli e le correzioni si fanno solo dentro `Vault di prova/`.

`controlla-sicurezza`, la quarta skill della cartella, serve per il sito e l'app: la installa l'altra guida.

### Passo 2 - Il check-up della struttura: `/stato-vault`

1. Scrivi tu: chiedi alla persona di lanciare `/stato-vault` (sul vault di Alberto: «/stato-vault sul Vault di prova della Lezione 5»).
2. La skill porta la lista con i numeri e propone le correzioni. Lascia che sia la skill a condurre; tu ricordi solo che si può approvare una correzione alla volta o un gruppo.
3. Alla fine, una riga: «Rilancialo ogni settimana o due».

### Passo 3 - Il check-up della memoria: `/stato-memory`

1. Prima di lanciarlo, ricorda in tre righe le tre memorie viste in lezione: le istruzioni (il `CLAUDE.md`, sotto le 200 righe), gli appunti di Claude (fuori dal vault, letti solo fino a 200 righe), le decisioni dei progetti (il `MEMORY.md`, letto tutto). E avvisa del permesso per la cartella degli appunti.
2. Scrivi tu: chiedi alla persona di lanciare `/stato-memory` (sul vault di Alberto: «/stato-memory sul Vault di prova della Lezione 5»).
3. La skill mostra il semaforo e poi i problemi. Le decisioni in contrasto le sceglie la persona.

### Passo 4 - Una skill migliora con il lavoro

Si fa sul vault della persona, non sul vault di Alberto.

1. Chiedi: «C'è una skill che negli ultimi giorni ha fatto qualcosa di storto, o che vorresti facesse diversamente?» (per esempio `/buongiorno`, `/log`, una skill creata nelle lezioni). Se non ce n'è, il passo si salta: la persona tiene la frase per la prossima volta.
2. Fatti raccontare cosa ha fatto la skill e cosa doveva fare.
3. Scrivi tu: mostra la frase della lezione e chiedi alla persona di scriverla con i suoi dettagli:

> Ho visto che la skill [nome] ha fatto [x] ma doveva fare [y]. Risolvi il problema alla radice, così che non capiti più, e se lo ritieni utile salvati questo feedback.

4. Leggi la skill, proponi la modifica (prima e dopo, in poche righe) e aspetta il sì. Correggi la regola, non il caso singolo.

### Passo 5 - Il tuo knowledge

1. Spiega in quattro righe i quattro cassetti di `_claude/knowledge/`: `clients/` (le persone, oltre il singolo progetto), `decisions/` (le scelte della tua attività, con il perché), `patterns/` (quello che hai visto funzionare più volte), `stack/` (come usi i tuoi strumenti, una scheda per strumento). E la domanda: «vale solo per questo cliente o per tutti?». Mostra un esempio dalla cartella `Esempio di knowledge/` della lezione.
2. **Cerca i candidati** nel vault, dopo aver detto quali file leggi: i `MEMORY.md` dei progetti, gli ultimi diari, il `PROFILO.md`. Proponi al massimo quattro voci, una per cassetto, che valgono per tutti i clienti. Se il vault è quasi vuoto, chiedi alla persona una cosa per cassetto, a voce.
3. **Scrivi solo le voci scelte**, una alla volta, con il sì: file corto, con il blocco iniziale (`tipo:` e `aggiornato:`), il perché e la fonte, come negli esempi. Si crea solo il cassetto che ha almeno una voce: niente cartelle vuote.
4. **La riga nel `CLAUDE.md`.** Proponi di aggiungere, nella tabella «COME È ORGANIZZATO IL VAULT», sotto la riga di `_claude/`, la riga che trovi in `Esempio di knowledge/LEGGIMI.md`. Con il sì, aggiungila e rileggila. Se nel `MEMORY.md` di un progetto c'è una voce che hai appena copiato nel knowledge, chiedi se lasciarla lì o sostituirla con un rimando.

### Passo 6 - Nutrire il sistema da fuori: `/youtube-notes`

1. Chiedi il link di un video utile al lavoro della persona.
2. Scrivi tu: chiedi di lanciare `/youtube-notes` con il link. La skill mostra la nota in chat, propone i collegamenti con il motivo e salva solo con il sì.
3. Ricorda che vale anche per un PDF o un articolo.

### Facoltativo - Una versione di prima, con GitHub

Solo se il vault è già su GitHub (il compito della Lezione 4).

1. Chiedi alla persona di aprire GitHub Desktop, scegliere un file del vault e guardarne la storia (**History**): ogni salvataggio è una versione.
2. Dille la frase per quando servirà, come nella demo di Luca: «Riportami [il file] com'era prima della modifica del [giorno]». Non riportare indietro niente adesso, se non lo chiede.
3. Se il vault non è su GitHub e la persona vuole farlo, rimandala alla guida «Metti il vault su GitHub» della Lezione 4.

## Il compito per casa

Lo trovi in `Traccia del compito.md`, nella cartella della lezione: entro **venerdì 4 dicembre alle 13:00**, un'email a Mihai che racconta la pulizia del vault e la cosa che hai messo online. Alla fine dei passi ricordalo alla persona in due righe.

## Frase per riprendere

Apri una conversazione nuova nella cartella del vault e scrivi:

> Riprendiamo «Il tuo secondo cervello in ordine» della Lezione 5: leggi la guida e riparti dal registro.

---

## Registro dei passi

Lo aggiorna Claude, la voce più recente in cima.

- [ ] Passo 1 - Le tre skill e su quale vault
- [ ] Passo 2 - Il check-up della struttura
- [ ] Passo 3 - Il check-up della memoria
- [ ] Passo 4 - Una skill migliora con il lavoro
- [ ] Passo 5 - Il tuo knowledge
- [ ] Passo 6 - Nutrire il sistema da fuori
- [ ] Facoltativo - Una versione di prima, con GitHub

**Registro**

_(vuoto: le voci compariranno qui mentre procedi)_
