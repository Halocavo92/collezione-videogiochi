# API dei dati

## Un'API "simulata"

In questo progetto non esiste un'API remota o un database. I dati sono forniti da un
file locale, **`data.json`**, letto dal sito tramite JavaScript. Il file si comporta come se fosse la risposta di un server.

## Cosa contiene `data.json`

- **`meta`** — informazioni generali e l'elenco delle colonne della tabella (`columns`).
- **`items`** — la lista dei giochi, un oggetto per ogni gioco.

*Esempio di un gioco*:

```json
{
  "id": 1,
  "title": "Nebula Runner",
  "subtitle": "Studio Horizon",
  "category": "Azione",
  "description": "Runner fantascientifico con livelli veloci e ostacoli dinamici.",
  "fields": { "piattaforma": "PC", "difficolta": "Media", "voto": "8/10" }
}
```
## Dove vengono mostrati i dati

Nella pagina **`giochi.html`**: come **card** (`#cards-container`), come **tabella**
(`#table-container`) e nel **filtro per genere** (`#category-filter`), riempito in
automatico con le categorie trovate.
