# Skill pronte

Quattro skill già scritte. Ognuna è una cartella con dentro `SKILL.md`: le istruzioni che Claude segue. Non installano programmi e non mandano i tuoi file a nessun servizio.

| Skill | Cosa fa | Dove si installa |
|---|---|---|
| `stato-vault` | il check-up della struttura: collegamenti rotti, mappe da aggiornare, file fuori posto, progetti fermi | nel vault |
| `stato-memory` | il check-up della memoria: quanto sono pieni istruzioni, appunti di Claude e MEMORY dei progetti, e cosa c'è scritto dentro | nel vault |
| `youtube-notes` | da un video (o un PDF, un articolo) a una nota ordinata nelle Risorse | nel vault |
| `controlla-sicurezza` | il controllo del tuo sito o della tua app prima di dare il link a qualcuno | nelle skill personali |

## Le tre skill del vault

Lavorano sul tuo secondo cervello, quindi vanno nel vault, in `.claude/skills/`, accanto alle procedure che hai già.

Il modo più semplice è chiederlo a Claude, aperto nel vault: «installa nel vault le skill stato-vault, stato-memory e youtube-notes da skill-pronte della Lezione 5, e aggiungile alla tabella delle procedure nel CLAUDE.md». Claude ti dice cosa copia e dove, e aspetta il tuo sì. L'app chiede il permesso di scrivere in `.claude/`: va consentito.

A mano: copia le tre cartelle dentro `.claude/skills/` del vault (la cartella `.claude` è nascosta: nel Finder la vedi con Cmd + Maiusc + punto; su Windows, in Esplora file, «Visualizza», «Mostra», «Elementi nascosti»).

Per provarle apri una conversazione nuova nel vault e scrivi `/`: nel menu devono comparire. Se non compaiono, scrivi `/reload-skills`.

## `controlla-sicurezza`

Si usa nella cartella del progetto del sito o dell'app (`~/Desktop/_Progetti Sviluppo/nome-del-progetto/`), che sta fuori dal vault. Per questo **non va nel vault** ma nella cartella delle skill personali, che Claude vede da qualsiasi cartella:

- Mac: `~/.claude/skills/controlla-sicurezza/` (cioè la cartella `.claude` dentro la tua cartella utente)
- Windows: `C:\Users\<il-tuo-nome>\.claude\skills\controlla-sicurezza\`

1. Apri la cartella `.claude` nella tua cartella utente. Se non la vedi, è normale: è nascosta, come sopra.
2. Se dentro non c'è una cartella `skills`, creala.
3. Copia dentro la cartella `controlla-sicurezza` (tutta). Il risultato deve essere `.claude/skills/controlla-sicurezza/SKILL.md`.
4. Apri una conversazione nuova nella cartella del progetto e scrivi `/`: nel menu deve comparire `controlla-sicurezza`. Se non compare, scrivi `/reload-skills`.

Se preferisci, chiedilo a Claude: «installa la skill controlla-sicurezza da skill-pronte nelle mie skill personali, in ~/.claude/skills: spiegamela prima». Claude ti dice cosa copia e dove, e aspetta il tuo sì. L'app può chiederti un permesso, perché `.claude` è una cartella speciale: va consentito.

**Quando usarla.** Prima di dare a qualcuno il link del tuo sito o della tua app, e ogni volta che aggiungi una funzione che tocca i dati (un modulo, un accesso con password, una tabella nuova). Per capire gli strumenti che controlla (GitHub, Vercel, Supabase e le chiavi) leggi la scheda «Gli strumenti per mettere online».
