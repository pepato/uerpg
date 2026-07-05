# Uallera — Scheda Personaggio online

Scheda personaggio statica per il motore **Uallera** (versione D10), consultabile ed editabile nel browser. Non serve un server, un database o un account: tutto lo stato della scheda è codificato nell'URL della pagina.

## Come funziona il salvataggio

- Ogni modifica alla scheda aggiorna automaticamente l'indirizzo del browser (dopo `#s=`).
- Il link completo (mostrato in fondo alla pagina, sezione "Salvataggio & Link scheda") **è** il salvataggio: copialo e conservalo (segnalibro, chat, note) per ritrovare la scheda in seguito.
- Ogni personaggio ha un "numero di fascicolo" fisso, generato alla creazione, che resta lo stesso anche quando il link cambia per via delle modifiche.
- Puoi anche scaricare un backup `.json` della scheda e ricaricarlo in seguito con "Carica backup", indipendentemente dal link.
- Non essendoci un server, **due persone con lo stesso link vedono la stessa istantanea, ma se lo modificano entrambe si generano due link diversi** (l'ultimo salvato da ciascuno). Va bene per l'uso previsto: ogni giocatore ha la propria scheda e il proprio link.

## Come mettere la pagina online con GitHub Pages

1. Crea un nuovo repository su GitHub (es. `uallera-schede`), pubblico.
2. Carica il file `index.html` (e questo `README.md`, opzionale) nella root del repository.
3. Vai su **Settings → Pages** del repository.
4. In "Build and deployment", scegli **Deploy from a branch**, branch `main`, cartella `/ (root)`. Salva.
5. Dopo un minuto la scheda sarà online all'indirizzo:
   `https://<tuo-utente>.github.io/<nome-repo>/`
6. Condividi quell'indirizzo con i giocatori: ognuno apre la pagina, compila la propria scheda e alla fine copia il proprio link personale (con `#s=...`) per ritrovarla in futuro.

## File

- `index.html` — l'intera app (HTML + CSS + JS), un solo file, nessuna build necessaria.

## Note tecniche

- Compressione dello stato tramite [LZString](https://github.com/pieroxy/lz-string) (caricata da CDN pubblico).
- Nessun dato lascia il browser: non c'è tracciamento, non ci sono chiamate a server esterni a parte il caricamento del font e della libreria di compressione.
- Funziona offline una volta caricata la pagina, salvo il primo caricamento di font/libreria.
