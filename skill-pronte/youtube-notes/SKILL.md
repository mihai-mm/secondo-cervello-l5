---
name: youtube-notes
description: >
  Trasforma un video YouTube in una nota ordinata dentro le Risorse del tuo
  secondo cervello: punti chiave, esempi, perché ti serve, e i collegamenti
  alle note a cui si lega, ognuno con il suo motivo. Prima mostra la nota in
  chat; la salva solo con il tuo sì. Usala quando incolli un link YouTube e
  vuoi prendere appunti, dici "riassumi questo video", "salva le note di
  questo video", oppure /youtube-notes. Vale anche per un PDF o un articolo.
---

# /youtube-notes - Nutrire il secondo cervello da fuori

Il secondo cervello non vive solo del tuo lavoro: lo nutri anche con quello che impari fuori. Questa skill prende un video e ne fa una nota ordinata, dentro le Risorse, collegata al resto.

> **Per Claude.** Chi la lancia non è tecnico: parla semplice. La nota si mostra **sempre** prima in chat; si salva nel vault **solo dopo un sì esplicito**. Valgono le regole del `CLAUDE.md` del vault.

## 1. Il testo del video

1. Prendi il link del video.
2. Prova a leggere titolo, canale e trascrizione con gli strumenti che hai.
3. Se non ci riesci (YouTube spesso blocca la lettura automatica), non insistere. Chiedi alla persona di incollarti la trascrizione e spiegale come si fa: «Apri il video su YouTube. Sotto il video clicca **...altro**, poi **Mostra trascrizione**. A destra compare il testo: selezionalo tutto, copialo e incollalo qui». Funziona su qualsiasi computer.

## 2. La nota, in chat

- **Titolo** del video, canale, link e data di oggi.
- **In una riga**: di cosa parla.
- **Punti chiave**: quello che conta, con parole tue, non la trascrizione.
- **Esempi, numeri, frasi** utili, se ci sono, con il minuto del video quando lo sai.
- **Perché ti serve**: una riga su come si lega al lavoro della persona. Chiedila a lei se non è chiaro.

Se la trascrizione è lunghissima, tieni la sostanza: la nota serve a ritrovare il pensiero, non a ricopiare il video.

## 3. Dove va

Le Risorse stanno in `3-Resources/`, con l'ingresso `3-Resources/_index.md`. La prima volta proponi una sottocartella, per esempio `3-Resources/YouTube/`, e chiedi se va bene. Se la persona tiene le Risorse altrove, usa quella cartella.

## 4. I collegamenti, con il motivo

Cerca nel vault le note a cui il video si lega (un progetto, un cliente, un'altra risorsa) e proponi i collegamenti. Ognuno con una frase che dice **perché**: la nota conferma, estende o contraddice qualcosa che c'è già. Un collegamento senza motivo non aiuta a ritrovare niente.

## 5. Salva, solo con il sì

Mostra la nota finita con i collegamenti e il percorso in cui la salvi, e chiedi: «La salvo?». Dopo il sì:

1. scrivi il file, con il blocco iniziale (`tipo: risorsa` e `aggiornato:` con la data di oggi);
2. aggiungi una riga in `3-Resources/_index.md` (se esiste) con il collegamento e una frase su cosa contiene;
3. non sovrascrivere mai una nota che esiste già senza chiedere.

Chiudi con: «Più lo nutri da fuori, più diventa tuo».

## Oltre YouTube

Per un PDF o un articolo vale lo stesso: la persona lo mette in `0-Inbox/` (o ti dà il link dell'articolo), tu ne ricavi il testo, e la nota segue gli stessi passi.
