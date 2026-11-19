# Il tuo sito e la tua prima app

In lezione hai visto nascere il sito del Birrificio: struttura, design, modifiche a parole, poi online con un link. E poi un foglio di contatti diventare un'app vera, con i dati salvati in un database.

Qui fai lo stesso con una cosa tua. Tre strade, scegli tu:

1. **Un sito**: il sito della tua attività, una pagina per un progetto o un evento.
2. **Il mini-CRM**: dal foglio di partenza della lezione (`mini-crm-partenza.xlsx`) a un'app con contatti, aziende e trattative.
3. **Un'app tua**: parti da un tuo foglio (un registro, un elenco di fornitori, le ore di lavoro) e lo trasformi in un'app.

Puoi farne una sola, o il sito e poi l'app. In aula o a casa: decidi tu.

## Cosa avrai alla fine

- **Una cartella per il progetto**, fuori dal vault, in `_Progetti Sviluppo` sul Desktop: il codice ha la sua casa, il vault resta per la conoscenza.
- **Il sito o l'app sul tuo computer**, che apri nel browser prima che lo veda qualcuno.
- **Una copia su GitHub**, privata, con tutte le versioni.
- **Un link** che funziona da qualsiasi computer e dal telefono, pubblicato con Vercel.
- **Per l'app: i dati in Supabase**, protetti da regole che fanno entrare solo te.
- **Un controllo di sicurezza** fatto con `/controlla-sicurezza` prima di dare il link a qualcuno.

## Cosa ti serve prima di partire

- L'app di Claude per computer, e la cartella della lezione nel vault, in `0-Inbox/`.
- GitHub Desktop, installato e collegato al tuo account GitHub (il compito della Lezione 4). Se non l'hai fatto, Claude ti guida.
- Gli account di Vercel e, per l'app, di Supabase: si creano durante la guida, entrando con il tuo account GitHub.
- La scheda **«Gli strumenti per mettere online»**, nella cartella della lezione: a cosa serve ogni strumento, quanto costa, dove vanno le chiavi. Vercel è gratis solo per uso personale: per il sito della tua attività chiede il piano Pro.
- Per un'app tua: il tuo foglio, in Excel, Numbers o Google Fogli. All'inizio usa dati finti o poche righe: i dati veri dei clienti entrano solo dopo il controllo di sicurezza.

## Come si usa

La guida ha due parti.

1. **Nel vault, per preparare.** Apri una conversazione nella cartella del vault e scrivi:

> Leggi «Il tuo sito e la tua prima app» nella cartella della Lezione 5 e guidami.

Claude ti chiede cosa vuoi costruire, crea la cartella del progetto fuori dal vault e ci copia dentro quello che serve, compresa questa guida.

2. **Nella cartella del progetto, per costruire.** Apri nell'app una conversazione nuova scegliendo la cartella del progetto (non il vault) e scrivi:

> Leggi GUIDA.md e guidami.

Per riprendere un altro giorno, la frase è in fondo alla guida.

## Se qualcosa non va

- **Claude dice che non trova GUIDA.md**: la conversazione è aperta nella cartella sbagliata. Aprine una nuova scegliendo la cartella del progetto.
- **Compare un errore**: è normale, fa parte del lavoro. Incollalo a Claude, o mandagli uno screenshot: lo legge e lo sistema.
- **Vercel dice che il progetto non si pubblica**: copia il messaggio rosso dalla pagina del progetto su Vercel e incollalo a Claude.
- **Le chiavi**: non si incollano mai in chat. Claude ti dice in quale file o in quale impostazione vanno, e lì le incolli tu.

---

## Da qui in giù è per Claude: non devi leggerlo

## Dove sei

Claude aggiorna queste righe alla fine di ogni passo, e il registro in fondo al file.

- **Cosa costruiamo**: -
- **Cartella del progetto**: -
- **Passo attuale**: -
- **Link online**: -

## Regole

Valgono insieme a quelle del `CLAUDE.md` della cartella in cui lavori; se qualcosa è in conflitto, valgono quelle, e lo dici.

1. **Sei la guida, un passo alla volta.** Mai due passi senza la conferma della persona. Una domanda alla volta, con opzioni numerate quando servono.
2. **La persona non sa programmare e non deve impararlo.** Le fai vedere il flusso, non il codice. Niente gergo: se un termine serve, lo spieghi in una frase.
3. **Annuncia prima di creare, installare o pubblicare.** Dici cosa stai per fare e aspetti il sì. Account, progetti su Supabase e pubblicazioni li fa la persona, con te che la guidi.
4. **La strada più semplice.** Il sito e l'app si fanno con pagine semplici (HTML, CSS e JavaScript), senza programmi da installare e senza una fase di costruzione: si aprono con un doppio clic e Vercel le pubblica così come sono. Proponi un'altra tecnologia solo se la persona chiede qualcosa che così non si può fare, e spiega prima cosa comporta (per esempio installare Node.js).
5. **Le chiavi non si vedono mai in chat.** La chiave pubblica di Supabase («publishable», o «anon» nelle guide vecchie) può stare nel codice dell'app, perché i dati li proteggono le regole di accesso. La chiave segreta («secret» o «service_role») **non serve** a questa app e non deve finire né nel codice né su GitHub: se la persona la incolla da qualche parte, fermati e spiegale perché va cambiata.
6. **I dati veri dopo il controllo.** Con un foglio della persona, all'inizio si usano dati finti o poche righe. I dati veri dei clienti entrano in Supabase solo dopo `/controlla-sicurezza` senza problemi gravi, e con il suo sì.
7. **La persona fa i gesti della lezione.** Quando un passo dice «scrivi tu», mostra la frase e aspetta che la scriva lei: descrivere cosa vuole, chiedere una modifica, incollare un errore.
8. **Intoppi.** Se qualcosa non torna, chiedi cosa vede sullo schermo o uno screenshot, poi spiega: cosa è successo, perché, l'unica cosa da fare adesso e la strada alternativa. Due tentativi al massimo con lo stesso errore.

## Parte A - Nel vault: prepara la cartella

1. **Cosa costruiamo.** Chiedi quale delle tre strade (sito, mini-CRM, app tua). Se sceglie il sito, chiedi per chi è (la sua attività, un progetto, un evento) e se ha già testi, foto e logo nel vault. Se sceglie un'app sua, chiedi quale foglio e cosa ci fa oggi.
2. **Il nome della cartella.** Proponi un nome corto, minuscolo, con i trattini (`sito-studio-rossi`, `mini-crm`). La cartella va in `_Progetti Sviluppo` sul Desktop: sul Mac `~/Desktop/_Progetti Sviluppo/[nome]/`, su Windows `C:\Users\[nome-utente]\Desktop\_Progetti Sviluppo\[nome]\`. Spiega in una riga perché fuori dal vault: il vault è per la conoscenza, il codice ha la sua casa.
3. **Cosa ci copi.** Annuncia l'elenco e aspetta il sì:
   - questa guida, con il nome `GUIDA.md`;
   - la scheda `Gli strumenti per mettere online.md`;
   - per il mini-CRM: `mini-crm-partenza.xlsx`;
   - per il sito: i testi, le foto e il logo che la persona ha scelto dal vault (copie: gli originali restano dove sono).
   Poi crea la cartella e copia i file con i comandi del terminale. Per l'app tua, il foglio lo copia la persona nella cartella (dal Finder o da Esplora file), perché sta fuori dal vault.
4. **La skill di sicurezza.** Se `controlla-sicurezza` non è ancora installata, proponi di installarla ora, seguendo `skill-pronte/LEGGIMI.md` della lezione: va nelle skill personali, non nel vault.
5. **Il passaggio.** Di' alla persona di aprire nell'app una conversazione nuova scegliendo la cartella del progetto e di scrivere «Leggi GUIDA.md e guidami». Aggiorna «Dove sei» nella copia `GUIDA.md` del progetto e scrivi nel registro di questa guida, nel vault, quale progetto è partito e dove.

## Parte B - Nella cartella del progetto: costruisci

All'avvio: controlla di essere nella cartella del progetto (contiene `GUIDA.md`) e non nel vault. Leggi «Dove sei» e il registro: se ci sono passi fatti, riparti dal primo non spuntato.

### Il sito

1. **Struttura.** Scrivi tu: chiedi alla persona di descrivere il sito con parole sue, come in lezione: «Fammi il sito di [chi]: [le sezioni che vuole]». Proponi le pagine o le sezioni, poche: per un sito vetrina basta spesso una pagina sola, con chi siamo, cosa facciamo, dove trovarci e i contatti.
2. **Design.** Chiedi lo stile: colori, caratteri, l'atmosfera in tre parole, un sito che le piace. Usa i testi e le foto copiati dal vault; dove mancano, scrivi testi provvisori chiaramente segnati come da sostituire, e non inventare fatti (prezzi, orari, numeri).
3. **Guarda.** Scrivi i file e apri la pagina nel browser (sul Mac `open index.html`; su Windows `start index.html`). Chiedi di guardarla anche stringendo la finestra, come sarà sul telefono.
4. **Modifica.** Scrivi tu: chiedi alla persona due o tre modifiche a parole, come a un grafico («il titolo più grande», «togli questa sezione»). Falle, poi riapri la pagina.
5. **Online.** Vai al passo «Online» più sotto, poi al controllo di sicurezza.

### Il mini-CRM o un'app tua

1. **Il foglio.** Leggi il foglio (`mini-crm-partenza.xlsx`: aziende, persone, commerciali, opportunità; oppure quello della persona) e spiega in tre righe cosa diventa: ogni foglio una tabella, ogni colonna un campo.
2. **Descrivi.** Scrivi tu: chiedi alla persona di dire cosa vuole fare con l'app, con parole sue. Per esempio: «Ho questo foglio con i miei contatti e le trattative. Fammi un'app dove li vedo, ne aggiungo di nuovi, cambio lo stato di una trattativa e li cerco. Solo io posso entrare».
3. **Il piano.** Prima di scrivere codice, proponi un piano corto: le tabelle, le schermate, l'accesso con password, e cosa farà la persona su Supabase. Aspetta il sì.
4. **Le scelte.** Fai le domande che servono, una alla volta («lo stato della trattativa da un elenco fisso, Lead, Proposta, Negoziazione, Chiusa, o libero?»). Costruire è una conversazione.
5. **Supabase, il progetto.** Guida la persona a crearlo su supabase.com (entra con GitHub, **New project**, regione europea, la password del database la genera Supabase e la salva lei nel suo gestore di password: non in chat). Avvisa che un progetto gratuito si mette in pausa dopo una settimana senza uso, e si riattiva dal pannello.
6. **Le tabelle e le regole.** Scrivi il codice SQL che crea le tabelle, attiva le regole di accesso (RLS) su ognuna e dà accesso in lettura e scrittura solo a chi ha fatto l'accesso (il ruolo `authenticated`), compresi i permessi (GRANT) per quel ruolo. Mettilo in un file `supabase.sql` nella cartella, spiegalo in tre righe e chiedi alla persona di incollarlo in **SQL Editor** su Supabase e premere **Run**. Se compare un errore, fattelo incollare.
7. **L'accesso solo per te.** Guida la persona: in **Authentication**, **Users**, **Add user**, crea il suo utente con email e password; poi, nelle impostazioni dell'accesso, spegne **Allow new users to sign up**, così nessun altro può registrarsi.
8. **La chiave pubblica.** Chiedi alla persona di aprire **Project Settings**, **API Keys**, e di copiare l'indirizzo del progetto e la chiave **publishable**. Prepara un file `config.js` con due righe da completare, e dille di incollarle lei, salvando il file. La chiave **secret** non serve: non va copiata.
9. **L'app.** Scrivi le pagine: accesso con email e password, l'elenco con la ricerca, l'aggiunta e la modifica. Aprila nel browser come per il sito e prova con la persona: entra, aggiunge un contatto, cambia lo stato di una trattativa.
10. **I dati del foglio.** Spiega come portarli dentro: la persona esporta ogni foglio in CSV (da Excel, Numbers o Google Fogli) e lo importa in Supabase dal **Table Editor** (**Insert**, **Import data from CSV**), oppure tu prepari i comandi SQL dal file. Per il foglio della persona, prima poche righe o dati finti (regola 6).
11. **L'errore.** Prima o poi qualcosa si rompe: quando succede, fai vedere che lo leggi e lo sistemi. Una frase: «L'errore non è un muro: lo incolli a Claude e si va avanti».
12. **Online**, poi il controllo di sicurezza.

### Online

1. **Su GitHub.** Prima crea un file `.gitignore` che esclude i file con le chiavi segrete (`.env*`) e i file di sistema (`.DS_Store`). Poi guida la persona in GitHub Desktop: **File**, **Add Local Repository**, sceglie la cartella del progetto (se dice che non è un repository, **create a repository** lì), poi **Publish repository** lasciando la spunta su **Keep this code private**.
2. **Su Vercel.** La persona entra su vercel.com con **Continue with GitHub**, poi **Add New**, **Project**, sceglie la copia appena pubblicata e preme **Deploy**. Se Vercel chiede di dargli accesso alla copia su GitHub, va consentito solo per quella.
3. **Il link.** Dopo un minuto c'è un indirizzo che finisce con `.vercel.app`: la persona lo apre, anche dal telefono. Scrivilo in «Dove sei».
4. **Ogni modifica, da qui in poi**: la chiedi a Claude, la guardi nel browser, la salvi con GitHub Desktop (**Commit**, poi **Push origin**) e Vercel la mette online da solo.
5. Ricorda in una riga: il piano gratuito di Vercel è per uso personale; per il sito della sua attività serve il piano Pro (vedi la scheda).

### Prima di dare il link: `/controlla-sicurezza`

Scrivi tu: chiedi alla persona di lanciare `/controlla-sicurezza` nella cartella del progetto. Se la skill non compare, installala prima (Parte A, punto 4). Per l'app, i dati veri entrano solo dopo un controllo senza problemi gravi.

### Una modifica a voce (facoltativo)

Scrivi tu: la persona chiede una modifica nuova, per esempio «aggiungi la data del prossimo contatto» o «fammi filtrare le trattative per stato». Falla, salvala su GitHub e guarda con lei che il link si aggiorna da solo.

## Il compito per casa

Lo trovi in `Traccia del compito.md`, nella cartella della lezione: entro **venerdì 4 dicembre alle 13:00**, un'email a Mihai che racconta la pulizia del vault e la cosa che hai messo online, con il link. Alla fine ricordalo alla persona in due righe.

## Frase per riprendere

Apri una conversazione nuova nella cartella del progetto e scrivi:

> Riprendiamo: leggi GUIDA.md e riparti dal registro.

---

## Registro dei passi

Lo aggiorna Claude, la voce più recente in cima.

- [ ] Parte A - Cartella del progetto pronta
- [ ] Il sito, oppure l'app: costruito e provato sul computer
- [ ] Online: GitHub e Vercel, il link funziona
- [ ] Controllo di sicurezza fatto
- [ ] Una modifica a voce (facoltativo)

**Registro**

_(vuoto: le voci compariranno qui mentre procedi)_
