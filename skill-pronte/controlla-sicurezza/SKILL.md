---
name: controlla-sicurezza
description: >
  Controlla la sicurezza del sito o dell'app che la persona ha costruito con Claude (sito vetrina,
  mini-CRM, app con database su Supabase, pubblicata su Vercel o simili): chiavi finite nel codice,
  su GitHub o nel sito online, dati leggibili da chiunque, registrazione aperta a tutti, pagine e
  funzioni private raggiungibili, moduli usabili per lo spam. Prima controlla senza toccare niente
  e consegna una lista in parole semplici, ognuna con quanto è grave; poi, solo se la persona dice
  sì, corregge un problema alla volta e ricontrolla. Usala per «controlla la sicurezza del mio
  sito», «la mia app è sicura?», «prima di dare il link ai clienti controlla che sia tutto a
  posto», «ho messo una chiave nel codice, è un problema?», oppure /controlla-sicurezza. Solo su
  siti e app della persona, mai su siti di altri.
---

# Controlla sicurezza

Chi usa questa skill non è un programmatore: ha costruito un sito o un'app parlando con Claude e vuole sapere se può darne il link ad altri senza rischi. Parla semplice, senza gergo. Quando una parola tecnica serve (per esempio «chiave»), spiegala la prima volta in mezza riga.

Quattro regole che valgono sempre:

1. **Prima si controlla, poi si corregge.** Durante il controllo non modifichi file, impostazioni o dati. Correggi solo dopo il sì della persona, un problema alla volta.
2. **Solo sui siti e sulle app della persona.** Se il link non è suo (un concorrente, un cliente che non ha chiesto niente), non fai nessun controllo e spieghi perché: provare la sicurezza di un sito altrui senza permesso non si fa.
3. **Nessuna chiave e nessun dato personale a schermo.** Non apri e non stampi i file con le chiavi (`.env`, `.env.local`), non mostri il contenuto delle righe trovate, non stampi le risposte del database. Usi solo i comandi scritti qui, che mostrano nomi di file, numeri di riga, codici e dimensioni. Se la persona incolla una chiave in chat, dille di non farlo più e trattala come esposta.
4. **Nessuna promessa di sicurezza totale.** Il controllo trova i problemi più comuni per chi parte da zero. Se non trovi niente, dici «nei controlli che ho fatto non ho trovato problemi», non «il sito è sicuro».

## 1. Cosa controlliamo

Chiedi alla persona, una domanda alla volta, solo quello che non sai già:

- **il link** del sito o dell'app online, se c'è;
- **la cartella del progetto** sul computer (di solito in `~/Desktop/_Progetti Sviluppo/`, fuori dal vault). Se la sessione è aperta altrove, chiedi il percorso e lavora su quello;
- se l'app **salva dati** (contatti, clienti, ordini) e dove: Supabase, un foglio Google, un file;
- se c'è **un accesso con password** e chi deve poter entrare (solo lei, i colleghi, i clienti).

Poi guarda da solo il progetto: che file ci sono, che strumenti usa (cerca nel codice parole come `supabase`, `vercel`, `.from(`), se c'è una cartella pubblicata (`dist/`, `build/`, `out/`, `.next/`) e se è collegato a GitHub. Per l'indirizzo della copia su GitHub usa `git remote -v | sed -E 's#://[^@/]+@#://#'` (toglie eventuali password dall'indirizzo). Per sapere se è pubblica: `curl -s -o /dev/null -w "%{http_code}\n" https://github.com/<utente>/<nome>` risponde `200` se chiunque la vede, `404` se è privata o non esiste; in quel caso chiedi alla persona, che lo vede su github.com accanto al nome («Private» o «Public»). Se la cartella non è collegata a git, i controlli sulla storia si saltano.

Riassumi in tre righe cosa hai capito («È un sito vetrina su Vercel, senza dati» oppure «È un mini-CRM: i contatti stanno su Supabase, l'app è online su Vercel, nessun accesso con password») e chiedi se è giusto prima di partire.

## 2. I controlli, in ordine di importanza

Fai solo quelli che servono a quel progetto. Un sito vetrina senza dati salta il punto B. Tutti i comandi si lanciano dalla cartella del progetto.

### A. Chiavi e password finite nel posto sbagliato

Una **chiave** è un codice che dà accesso a un servizio (il database, un'intelligenza artificiale, i pagamenti). Ce ne sono di due tipi:

- **pubbliche**, fatte apposta per stare nel sito: su Supabase la «publishable key» (`sb_publishable_...`) o, nelle guide più vecchie, la «anon key». Non sono un problema, se le regole del punto B sono a posto;
- **segrete**, che danno pieno accesso: su Supabase la «secret key» (`sb_secret_...`) o la vecchia «service_role»; le chiavi delle intelligenze artificiali (OpenAI `sk-proj-...`, Anthropic `sk-ant-...`, OpenRouter `sk-or-...`), di Stripe (`sk_live_...`, `sk_test_...`), password di email o di database. Queste non devono mai stare nel codice del sito, nella cartella pubblicata né su GitHub.

Il posto giusto per le chiavi segrete è un file `.env` (o `.env.local`) sul computer, escluso da GitHub, e le impostazioni del progetto su Vercel. Una chiave trovata lì è al suo posto.

Nei comandi qui sotto, al posto della parola `SEGRETI` scrivi per intero questo elenco (comprende la vecchia service_role anche nella forma in codice che ha dentro il sito):

```
sb_secret_|sk_live_|sk_test_|rk_live_|sk-(proj|ant|or)-|sk-[A-Za-z0-9]{32}|SERVICE_ROLE|service_role|c2VydmljZV9yb2xl|NlcnZpY2Vfcm9sZ|zZXJ2aWNlX3JvbGU|PRIVATE KEY
```

Cosa controlli:

1. **Nei file del progetto.** Usa questo comando, scritto così, e non lo strumento di ricerca di Claude. In Claude Code la parola `grep` da sola chiama uno strumento che salta i file nascosti come `.env` e quelli esclusi da GitHub: `command grep` usa quello vero. Vale per tutti i comandi di questa skill. Mostra solo file e riga:
   `command grep -rnE --exclude-dir=node_modules --exclude-dir=.git "SEGRETI" . | cut -d: -f1,2`
   Come leggerlo: una riga in un `.env*` escluso da GitHub va bene; una riga nel codice o in `dist/`, `build/`, `out/`, `.next/` è grave.
2. **Chiavi segrete mandate al browser per sbaglio.** Nei siti costruiti con Next.js o Vite le variabili che iniziano con `NEXT_PUBLIC_`, `VITE_`, `REACT_APP_` o `PUBLIC_` finiscono nel sito. Se una chiave segreta ha uno di questi nomi, è online. Il comando mostra solo il nome della variabile:
   `command grep -rnoE --exclude-dir=node_modules --exclude-dir=.git "(NEXT_PUBLIC|VITE|REACT_APP|PUBLIC)_[A-Z0-9_]*(SECRET|SERVICE_ROLE|PRIVATE|PASSWORD|OPENAI|ANTHROPIC|OPENROUTER)[A-Z0-9_]*" .`
3. **Il file delle chiavi è su GitHub?** `git ls-files | command grep -iE '(^|/)\.env'` elenca i file `.env` salvati su GitHub. Se esce qualcosa (diverso da un `.env.example` senza valori), quel file è su GitHub anche se oggi compare in `.gitignore`. Poi `git log --all --format= --name-only | command grep -iE '(^|/)\.env' | sort -u` dice se lo è mai stato in passato.
4. **Nella storia di GitHub.** Una chiave cancellata dal codice resta nelle versioni vecchie: `git log --all --oneline -G "SEGRETI"`. Se esce almeno una riga, una chiave segreta è stata salvata in passato. Non aprire le versioni per guardarla.
5. **Nel sito online.** Quello che il browser scarica lo vede chiunque. Se c'è una cartella pubblicata (`dist/`, `build/`, `out/`, `.next/static/`), il comando del punto 1 l'ha già guardata tutta. In più, controlla il sito vero: scarica la pagina con `curl -sL <link>` (la `L` segue i reindirizzamenti), trova i file `.js` che carica e per ognuno conta le chiavi senza stamparle: `curl -sL <link-del-file.js> | command grep -cE "SEGRETI"`. Un numero diverso da 0 è grave. Fai lo stesso con le pagine principali (per esempio `/admin`, se esiste).

### B. Dati leggibili o modificabili da chiunque

È l'errore più comune con Supabase, ed è grave: in un CRM ci sono i dati dei clienti. Supabase protegge ogni tabella con delle **regole di accesso** (si chiamano RLS, «Row Level Security»). Una tabella senza regole è leggibile e modificabile da chiunque abbia la chiave pubblica, che sta nel sito e quindi ce l'ha chiunque.

Cosa controlli:

1. **Il Security Advisor di Supabase.** Fai aprire alla persona il progetto su supabase.com, sezione **Advisors**, poi **Security Advisor**, e fatti leggere tutti gli avvisi rossi e gialli. Contano di più: tabella senza regole («RLS disabled»), regola che lascia fare tutto a tutti («allows unrestricted access»: è l'unico modo per vedere chi può anche scrivere o cancellare), vista che salta le regole («bypasses row-level security»), colonne sensibili esposte, cartella di file pubblica. Se la persona ha collegato Supabase a Claude, puoi leggerli tu, ma solo in sola lettura.
2. **Chi può registrarsi.** Se l'app ha l'accesso con password, fai aprire **Authentication** e guardare se è attivo «Allow new users to sign up». Se l'app è solo della persona o del suo team e la registrazione è aperta, chiunque si crea un account ed entra: va spenta, e i colleghi si invitano. E le regole devono dire «solo questo utente» o «solo questi utenti», non «chiunque abbia fatto l'accesso».
3. **La prova da fuori, in sola lettura.** Serve a confermare quello che dice l'Advisor. Prima fatti dire dalla persona, dal Table Editor di Supabase, che la tabella ha almeno una riga: su una tabella vuota la prova non dimostra niente. Poi usa **solo la chiave pubblica**, letta dal file senza mostrarla (sostituisci `.env.local`, l'indirizzo e la tabella con quelli veri):
   `K=$(command grep -hE "^(NEXT_PUBLIC_|VITE_)?SUPABASE_(ANON|PUBLISHABLE)[A-Z_]*KEY=" .env.local | head -1 | cut -d= -f2-); case "$K" in ""|sb_secret_*) echo "chiave pubblica non trovata";; *) curl -s -o /dev/null -w "%{http_code} %{size_download}\n" "<indirizzo-supabase>/rest/v1/<tabella>?select=*&limit=1" -H "apikey: $K";; esac`

   Se la chiave pubblica non sta in un file `.env` ma nel codice (succede nelle app fatte di sole pagine, per esempio in `config.js`), leggila così, sempre senza mostrarla:
   `K=$(command grep -rhoE --exclude-dir=node_modules --exclude-dir=.git "sb_publishable_[A-Za-z0-9_-]+" . | head -1); case "$K" in "") echo "chiave pubblica non trovata";; *) curl -s -o /dev/null -w "%{http_code} %{size_download}\n" "<indirizzo-supabase>/rest/v1/<tabella>?select=*&limit=1" -H "apikey: $K";; esac`
   Come leggerlo: `401` o `403` vuol dire chiusa; `404` vuol dire nome della tabella da ricontrollare; `200 2` vuol dire che da fuori non si legge niente; `200` con un numero più grande vuol dire che **chiunque legge quella tabella**. Se la chiave pubblica non è in un file (un sito senza `.env`), chiedi alla persona dove la usa il sito. Mai usare la chiave segreta per questa prova: salta le regole. **Non provare mai a scrivere, modificare o cancellare** per dimostrare un problema.
4. **Dati dentro il sito o in un foglio condiviso.** File `.csv`, `.json` o `.xlsx` con dati veri dentro il progetto (soprattutto in `public/`) sono leggibili da tutti, sul sito e su GitHub. Lo stesso vale per un foglio Google «pubblicato sul web» o condiviso con «chiunque abbia il link» da cui l'app legge i dati.
5. **Chi deve vedere i dati.** Se l'app è solo per la persona ma non c'è un accesso con password, chiunque abbia il link vede tutto: va detto chiaramente, anche se le tabelle hanno delle regole.

### C. Pagine e funzioni che dovrebbero essere private

1. **Le funzioni del server.** Cerca le cartelle `api/`, `app/api/`, `pages/api/` e `supabase/functions/`. Se una di queste usa la chiave segreta, salta le regole del database: deve controllare che chi la chiama abbia fatto l'accesso. Prova da fuori con una sola richiesta in lettura, senza accesso, guardando solo codice e dimensione: `curl -s -o /dev/null -w "%{http_code} %{size_download}\n" <link>/api/<nome>`. Un `200` con una risposta grande vuol dire che chiunque riceve quei dati.
2. **Le pagine.** Pagine o pulsanti per modificare o cancellare dati, pannelli di amministrazione, esportazioni: serve un accesso con password per arrivarci? Una pagina nascosta ma raggiungibile con il suo indirizzo è pubblica.

### D. Moduli che chiunque può usare

Se il sito ha un modulo (contatti, prenotazioni, iscrizione): dove finiscono i messaggi? C'è una protezione contro lo spam controllata dal server? Un modulo che manda email o scrive nel database senza nessun limite può essere usato per riempirli di spam. Guarda il codice e non fare prove di invio in massa. Un solo invio di prova è l'unica eccezione alla regola 1: proponilo, spiega che lascerà un messaggio di prova, e fallo solo con il sì della persona.

### E. Le basi

- Il sito si apre con `https://` (con Vercel di solito è automatico).
- Se il progetto ha `package-lock.json`, lancia `npm audit` e riporta solo gli avvisi «high» e «critical», spiegati in una riga. Se il file manca, salta e scrivilo fra le cose non controllate. Non lanciare `npm audit fix --force` e nessun comando che installa o scrive file.
- I link di anteprima (quelli che Vercel crea per ogni modifica) mostrano dati veri? Se sì, segnalalo.

## 3. Il risultato

Scrivi la lista in chat, in quest'ordine:

- **Grave** - da sistemare prima di dare il link a qualcuno (chiave segreta esposta, dati leggibili da chiunque, registrazione aperta su un'app privata, funzione del server aperta, dati dei clienti senza accesso con password).
- **Da sistemare** - un rischio vero ma meno urgente (modulo senza protezione dallo spam, avvisi «high» di `npm audit`).
- **Consiglio** - una buona abitudine (copia su GitHub privata invece che pubblica, avvisi minori).

Per ogni punto: cosa hai trovato, perché è un problema in una frase concreta («chiunque apra questo indirizzo vede nome e telefono dei tuoi clienti»), come lo hai verificato e cosa proponi. In fondo, una riga su **cosa non hai potuto controllare** (per esempio «il Security Advisor non l'abbiamo aperto»): non controllato non vuol dire a posto.

Proponi di salvare la lista come nota nel vault, dove la persona tiene il progetto, con la data nel nome (`controllo-sicurezza-AAAA-MM-GG.md`). Se non sai dov'è il vault, chiedi il percorso. **Mai nella cartella del sito**: tutto quello che sta lì può finire online.

## 4. Le correzioni, solo con il sì

Chiedi da quale problema partire (consiglia il primo «Grave»). Per ognuno:

1. spiega cosa cambierai, in due righe;
2. aspetta il sì;
3. fai la modifica più piccola che risolve;
4. ricontrolla con la stessa prova della sezione 2 e mostra il risultato;
5. chiedi se pubblicare la modifica (salvarla su GitHub e quindi online). Pubblicare è un'azione a parte: non farla senza il suo sì.

Casi particolari:

- **Una chiave segreta è finita nel codice, su GitHub o nel sito.** Toglierla dal codice non basta, perché resta nelle versioni vecchie e qualcuno potrebbe averla già copiata. Va **sostituita**, in quest'ordine:
  1. la persona crea una chiave nuova nel pannello del servizio (su Supabase: «Settings», poi «API Keys») e la incolla lei nel file `.env` e nelle impostazioni di Vercel, mai in chat;
  2. ripubblichi il sito (su Vercel le chiavi nuove valgono solo dalla pubblicazione successiva) e provate insieme che l'app funzioni;
  3. solo dopo la persona cancella la chiave vecchia;
  4. se era la vecchia «service_role» di Supabase: prima il sito passa alla chiave publishable al posto della vecchia anon, poi si disattivano le chiavi vecchie (si spengono insieme) e si revoca il vecchio «JWT secret». Segui la guida ufficiale di Supabase sulle chiavi esposte.
  Se il file `.env` era salvato su GitHub, toglilo con `git rm --cached <file>` (lo toglie da GitHub, non dal computer) e aggiungilo a `.gitignore`. Se la chiave stava nel sito perché la pagina ne ha bisogno (per esempio per chiamare un'intelligenza artificiale), spostarla nel `.env` con un nome che inizia per `NEXT_PUBLIC_` o `VITE_` la rimette online: quell'operazione va spostata in una funzione del server.
- **Tabella senza regole di accesso.** Attivare le regole senza scriverne nessuna blocca tutto, anche l'app. Prima scrivi con la persona chi deve poter leggere e modificare cosa (per esempio «solo io, dopo l'accesso con password»), poi proponi le regole, poi attivale e prova che l'app funzioni ancora.
- **Manca l'accesso con password.** È una modifica più grande: spiegala, chiedi se farla adesso o in un secondo momento, e fino ad allora consiglia di non dare il link a nessuno.

## Cosa questa skill non fa

- Non attacca, non riempie di richieste e non prova a entrare nei siti: legge, guarda e fa solo prove in lettura.
- Non controlla gli aspetti di privacy e legge (cookie, informativa, GDPR): se servono, lo dice e rimanda a un controllo a parte.
- Non legge e non scrive chiavi in chat. Quando una prova ne ha bisogno, il comando la legge dal file senza mostrarla.
