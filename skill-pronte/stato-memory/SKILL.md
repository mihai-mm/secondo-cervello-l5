---
name: stato-memory
description: >
  Check-up della MEMORIA di Claude. Misura quanto sono pieni i tre posti in
  cui Claude ricorda (le istruzioni nel CLAUDE.md, gli appunti automatici di
  Claude, il MEMORY.md di ogni progetto), poi rilegge cosa c'è scritto e
  trova decisioni in contrasto, informazioni superate, cose finite nel posto
  sbagliato, voci troppo lunghe. Propone cosa accorciare, unire o togliere;
  decidi tu. Usala quando dici "stato memory", "controlliamo la memoria",
  "puliamo la memoria di [progetto]", quando Claude Code avvisa che la
  memoria è quasi piena, oppure /stato-memory. Cadenza: una volta al mese.
---

# /stato-memory - Il check-up della memoria

La struttura può essere a posto, con i file al posto giusto, e la memoria essersi sporcata lo stesso: due decisioni che si contraddicono, un appunto vecchio, lo stato di oggi finito fra le decisioni. E la memoria non è infinita: oltre una certa lunghezza Claude non vede più tutto, o si confonde. Questa skill misura e poi pulisce.

> **Per Claude.** Chi la lancia non è tecnico: parla semplice. Le scelte le fa la persona: tu misuri, trovi e proponi. Niente si scrive o si toglie senza il suo sì. Valgono le regole del `CLAUDE.md` del vault; se qualcosa è in conflitto, valgono quelle e lo dici.

## Le tre memorie

| Memoria | Dove sta | Come la legge Claude | Il limite |
|---|---|---|---|
| **Le istruzioni** | `CLAUDE.md` del vault, più i file che richiama con `@` (per esempio `_claude/SOUL.md` e `_claude/PROFILO.md`) e il `CLAUDE.md` di ogni progetto | tutte, all'inizio di ogni sessione (quelle di un progetto quando si lavora lì) | più sono lunghe, meno le segue: sotto le 200 righe per file |
| **Gli appunti di Claude** (la memoria automatica) | fuori dal vault, nella cartella della memoria automatica di questo vault: un file per appunto e un indice, `MEMORY.md` | a ogni sessione legge solo le prime 200 righe dell'indice, o i primi 25 KB | sotto, ci sono gli appunti più recenti: se l'indice è troppo lungo, Claude non li vede |
| **Le decisioni dei progetti** | il `MEMORY.md` nella cartella di ogni progetto | tutto il file, quando si riprende quel progetto | nessun taglio, ma più è lungo più è facile che trovi due decisioni in contrasto o una vecchia |

## Passo 1 - Quanto sono pieni (sempre, prima di tutto)

Se la persona chiede di provare su un'altra cartella (per esempio il `Vault di prova` della lezione), considera quella cartella come se fosse il vault. Gli appunti di Claude di quella cartella non esistono: dillo e misura solo le altre due memorie.

1. **Le istruzioni.** Conta le righe del `CLAUDE.md` del vault e di ogni file che richiama con `@` (con un comando: `wc -l`), e dai il totale che Claude carica a ogni sessione. Conta anche i `CLAUDE.md` dei progetti.
2. **Gli appunti di Claude.** Il percorso della cartella lo trovi nelle tue istruzioni, nella parte sulla memoria automatica. Di solito è `~/.claude/projects/[nome-del-vault]/memory/`, dove il nome è il percorso del vault con un trattino al posto di ogni barra, spazio o punto. Conta le righe e i KB dell'indice `MEMORY.md` e quanti file ci sono. Se la cartella non c'è o è vuota, dillo: «Claude non ha ancora appunti automatici su questo vault». È normale.
   - Questa cartella sta fuori dal vault. Prima di aprirla, di' alla persona che l'app potrebbe chiedere un permesso: va scelto **Consenti**, mai l'opzione che blocca per sempre. Se non vuole, misura soltanto (con il comando) e salta il controllo del contenuto degli appunti.
3. **Le decisioni dei progetti.** Per ogni `MEMORY.md` in `1-Projects/` e `2-Areas/`: KB e righe, e in pagine (circa 3 KB a pagina).

Mostra il risultato in una tabella con un semaforo:

| Memoria | Verde | Giallo | Rosso |
|---|---|---|---|
| Ogni file di istruzioni | fino a 150 righe | 150-200 | oltre 200 |
| Indice degli appunti di Claude | fino a 150 righe e 20 KB | fino a 200 righe e 25 KB | oltre: una parte non viene letta |
| `MEMORY.md` di un progetto | fino a 10 KB | 10-20 KB | oltre 20 KB (circa 7 pagine) |

Poi chiedi da dove partire: dal rosso, da un progetto preciso, oppure da tutto.

## Passo 2 - Cosa c'è scritto

**Nel `MEMORY.md` di un progetto:**

1. **Decisioni in contrasto**: due voci che dicono cose diverse, e la vecchia non è segnata come superata. Mostra le due versioni con la data e chiedi quale vale. Non scegliere tu.
2. **Decisioni superate non segnate**: si segnano «SUPERATA il AAAA-MM-GG», con il rimando a quella nuova, senza cancellarle. Se la nuova **precisa** la vecchia senza sostituirla, la vecchia resta valida.
3. **Lo stato nel posto sbagliato**: sezioni come «a che punto siamo», «prossimi passi», «da fare». Sono fotografie che invecchiano: il loro posto è `## Stato corrente`, in cima al diario più recente in `attivita/`. Se il diario non c'è, chiedi dove metterle.
4. **Voci troppo lunghe**: una decisione si dice in poche righe, con il perché. Il come (i passaggi, i dettagli) va nel diario o in un documento del progetto: proponi la versione corta e dove spostare il resto.
5. **Cose che valgono per tutti i clienti**: se nel vault c'è `_claude/knowledge/`, proponi di spostarle lì, nel cassetto giusto.

**Nell'indice degli appunti di Claude:**

1. Ogni appunto deve stare su una riga sola, corta: il dettaglio sta nel suo file. Proponi le righe accorciate.
2. Appunti doppi o in contrasto: proponi di unirli, chiedendo quale versione vale.
3. Appunti superati: proponi di toglierli, con il sì.
4. Appunti nel posto sbagliato: una regola che vale sempre sta meglio nel `CLAUDE.md` del vault; una cosa che riguarda un solo cliente nel suo `MEMORY.md`.

**Nelle istruzioni (`CLAUDE.md`):**

1. Se un file supera le 200 righe, proponi cosa spostare: una procedura lunga diventa una skill; un dettaglio che serve ogni tanto va in un file in `_claude/` che Claude apre quando serve (citato nel `CLAUDE.md` con il suo nome, senza `@`).
2. Regole doppie o in contrasto: mostrale e chiedi quale tenere.

## Come procede

1. Porta la lista con i numeri: «2 decisioni in contrasto, 1 sezione di stato da spostare, l'indice degli appunti a 230 righe».
2. Chiedi se preferisce una modifica alla volta o un gruppo di modifiche simili approvate insieme.
3. Prima di una modifica grande (un file accorciato di molto): se il vault è su GitHub ogni versione resta e si recupera; se non lo è, proponi prima una copia del file in `4-Archives/`.
4. Applica solo quello che la persona conferma. Dopo ogni gruppo di modifiche rimisura e mostra il prima e il dopo.

## Alla fine

Tre righe: quanto erano pieni i file prima e dopo, cosa è stato sistemato, cosa resta in sospeso. Poi: «Una memoria pulita è ciò che fa la differenza tra risposte affidabili e un Claude che si confonde sui tuoi dati. Rilancia /stato-memory una volta al mese, o quando Claude Code ti avvisa che la memoria è quasi piena».
