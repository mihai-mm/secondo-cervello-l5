---
name: stato-vault
description: >
  Check-up della STRUTTURA del tuo secondo cervello: collegamenti che non
  portano più da nessuna parte, mappe dei progetti che non elencano tutti i
  file, file fermi nell'Inbox o fuori posto, progetti fermi da settimane,
  file senza il blocco iniziale. Porta la lista e propone le correzioni,
  una alla volta o a gruppi, solo con il tuo sì. Usala quando dici "stato
  vault", "controlliamo il vault", "facciamo manutenzione", oppure /stato-vault.
  Cadenza: ogni settimana o due.
---

# /stato-vault - Il check-up della struttura

Controlla che nel vault tutto sia al posto giusto e raggiungibile. È la gemella di `/stato-memory`, che invece controlla cosa c'è scritto dentro i file.

> **Per Claude.** Chi la lancia non è tecnico: parla semplice, una cosa alla volta. Non sistemare niente di nascosto: trovi, mostri, proponi e aspetti il sì. Valgono le regole del `CLAUDE.md` del vault; se qualcosa è in conflitto, valgono quelle e lo dici.

## Prima di cominciare: riconosci il vault

1. Controlla di essere nella cartella principale del vault: ci sono `CLAUDE.md`, `Home.md` e almeno `1-Projects/` (di solito anche le altre cartelle da `0-Inbox` a `4-Archives`). Se non li trovi, dillo e fermati: su una cartella qualsiasi non si inventano problemi.
2. Il vault del corso è organizzato così, e i controlli lo danno per buono:
   - ogni progetto in `1-Projects/[Nome]/` (e ogni area in `2-Areas/[Nome]/`) ha `CLAUDE.md`, `MEMORY.md` e la mappa `[Nome].md`, che collega tutti i file della cartella;
   - il diario sta in `attivita/`, un file per settimana (`2026-W47.md`), con `## Stato corrente` in cima;
   - `Home.md` collega ogni progetto e ogni area;
   - i file principali iniziano con un piccolo blocco (`tipo:` e `aggiornato:`).
   Se il vault è organizzato in un altro modo, chiedi alla persona come, con una domanda sola, e adatta i controlli.
3. **Leggi solo dentro il vault.** Salta `.obsidian/`, `.claude/`, `.git/` e `_attachments/`. Per `Daily/` e per le aree private chiedi prima se vanno incluse.
4. **Le cartelle delle lezioni** scaricate in `0-Inbox/` (per esempio `secondo-cervello-l5`) sono materiale del corso, con esempi inventati: non controllarne il contenuto. Contale come una voce sola fra i file fuori posto e chiedi se spostarle tutte insieme, per esempio in `3-Resources/Corsi/`, quando la persona ha finito di usarle.
5. **Se la persona chiede di provare su un'altra cartella** (per esempio il `Vault di prova` della lezione), considera quella cartella come se fosse il vault: controlli e correzioni solo lì dentro.

## Cosa controlla

1. **Collegamenti rotti**: un `[[Nome]]` o `[[percorso/Nome|testo]]` che porta a una nota che non esiste più (rinominata, spostata o mai creata). Per controllare togli il testo dopo `|` e la parte dopo `#`, poi cerca il file con quel nome o quel percorso.
2. **Mappe non aggiornate**: la mappa di un progetto che non collega un file della sua cartella (un diario, una chiamata, un documento nuovo). E `Home.md` che non collega un progetto o un'area.
3. **File fuori posto**:
   - file in `0-Inbox/` da più di due settimane (guarda la data nel nome o nel blocco iniziale; se non c'è, la data dell'ultima modifica);
   - file sciolti nella cartella principale del vault, oltre a quelli previsti (`CLAUDE.md`, `Home.md`, `LEGGIMI.md`, le dashboard, i PDF del pacchetto);
   - file che non sono collegati da nessuna parte.
4. **Progetti fermi**: un progetto il cui diario più recente (la settimana più alta nel nome, non il file modificato per ultimo) è più vecchio di tre settimane. Non è un errore: chiedi se il progetto è in pausa, finito (si può spostare in `4-Archives/`) o se il diario è rimasto indietro.
5. **Blocco iniziale mancante o vecchio** sui file principali di ogni progetto (`CLAUDE.md`, `MEMORY.md`, mappa, diario): manca il blocco, oppure `aggiornato:` dice una data più vecchia dell'ultima voce scritta nel file.
6. **Cartelle vuote** o rimaste a metà.

## Come procede

1. **Scansiona** con gli strumenti di ricerca e di lettura, dentro il vault. Non servono programmi da installare.
2. **Porta la lista**, raggruppata per tipo e con i numeri: «3 collegamenti rotti, 1 mappa da aggiornare, 2 file fermi nell'Inbox, 1 progetto fermo da quattro settimane». Per ogni problema: dove sta e cosa proponi.
3. **Chiedi come vuole procedere**: una correzione alla volta, oppure un gruppo di correzioni simili approvate insieme (per esempio tutti i collegamenti che hanno un solo candidato ovvio).
4. **Correggi solo con il sì**:
   - collegamento rotto con un solo candidato ovvio: proponi la correzione;
   - con più candidati: chiedi quale;
   - file nell'Inbox o sciolto: proponi dove spostarlo e di aggiungerlo alla mappa giusta;
   - mappa non aggiornata: proponi le righe da aggiungere, con una frase su cosa c'è in ogni file;
   - progetto fermo: chiedi cosa vuole fare, non decidere tu;
   - blocco iniziale: proponi di aggiungerlo o di aggiornare la data.
5. Nel dubbio su un file, non toccarlo: segnalalo e basta.

## Alla fine

Tre righe: cosa è stato sistemato, cosa resta in sospeso e perché. Poi: «Rilancia /stato-vault ogni settimana o due: è come riordinare la scrivania. Per controllare cosa c'è scritto nei file c'è /stato-memory».
