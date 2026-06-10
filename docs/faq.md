# Domande frequenti (FAQ)

### 1. Il sito funziona senza internet?

In parte. Le pagine e i dati (`data.json`) sono locali, quindi funzionano offline.
Però **Bootstrap viene caricato da internet (CDN)**: al primo avvio serve la
connessione per scaricare stile e funzioni (navbar, menu, ecc.). Dopo, finché
resta in cache, il sito funziona anche offline. Per renderlo davvero 100% offline
basterebbe scaricare i file di Bootstrap nella cartella del progetto.

### 2. Perché i dati non compaiono?

Quasi sempre perché la pagina è stata aperta con un **doppio click** sul file
(`file://`) invece che tramite un **server locale**. In quel caso il browser
blocca `fetch("data.json")` e compare un messaggio di errore rosso.
Soluzione: avvia il server (`python -m http.server 8000`) e apri
`http://localhost:8000`.

### 3. Dove si trova il file dei dati?

Nel file **`data.json`**, nella cartella principale del progetto. Contiene la lista
dei giochi e le informazioni delle colonne usate dalla tabella.

### 4. Come modifico o aggiungo i contenuti?

Apri **`data.json`** e modifica la lista `items`. Per aggiungere un gioco copia un
blocco esistente e cambia i valori:

```json
{
  "id": 9,
  "title": "Nuovo Gioco",
  "subtitle": "Studio Esempio",
  "category": "Azione",
  "description": "Breve descrizione del gioco.",
  "fields": {
    "piattaforma": "PC",
    "difficolta": "Media",
    "voto": "8/10"
  }
}
```

Salva e ricarica la pagina `giochi.html`: la card e la riga in tabella compaiono
da sole.

### 5. A cosa serve il file `script.js`?

È il "motore" del sito. Legge `data.json` con `fetch`, poi genera automaticamente
le **card** e la **tabella** dei giochi, gestisce il **filtro per genere**, aggiorna
il **contatore** e mostra il **messaggio di errore** se i dati non si caricano.

### 6. Perché la pagina Piattaforme non cambia se modifico `data.json`?

Perché `piattaforme.html` è una pagina **statica**: i suoi contenuti sono scritti a
mano nel file HTML. Solo `giochi.html` è collegata a `data.json` e si aggiorna da
sola. Se aggiungi una piattaforma nuova, aggiorna anche la pagina Piattaforme a mano.
