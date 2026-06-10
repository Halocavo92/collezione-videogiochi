# Installazione e Avvio

Questa guida spiega come scaricare e avviare il progetto sul tuo computer.

## Requisiti

- Un **Browser** moderno (Chrome, Firefox, Edge…)
- **Git** (per clonare la repository)
- **Python 3** per il server locale — in alternativa l'estensione **Live Server** di VS Code

## 1.Scaricare il Progetto
 
 Clonare la repository di GitHub con **Git**

    ```bash
    git clone https://github.com/Halocavo92/collezione-videogiochi.git
    cd collezione-videogiochi    
    ```
 Altrimenti puoi scaricare lo **ZIP** della repository da GitHub nella pagina della repository cliccando **Code --> Donload ZIP**

## 2.Avviare un server locale

 Ci sono due modi per poter visualizzare il progetto :

 **1. Python** :

 ```bash
 python -m http.server 8000
 ```

 **2.Live Server (VS Code)**:

 ** apri la cartella in VS Code, fai clic destro su
`index.html` e scegli **"Open with Live Server"**.

## 3.Aprire il sito nel browser

 Con il server Python attivo, vai su:
 
 ```text
 http://localhost:8000
 ```

 Si aprirà la home (`index.html`). Da lì usa la **navbar** per spostarti tra
 Home, Giochi e Piattaforme.

## 4. Problemi

**I dati non compaiono**
È quasi sempre perché la pagina è stata aperta con doppio click (`file://`) invece
che dal server. Apri il sito tramite `http://localhost:8000`.

**Errore "Address already in use" sulla porta 8000**
La porta è occupata da un altro programma. Usane un'altra, ad esempio:

```bash
python -m http.server 8080
```

e apri `http://localhost:8080`.

**Errore 404 su `data.json`**
Assicurati di aver avviato il server **dentro la cartella del progetto** (quella che
contiene `index.html` e `data.json`), non da una cartella superiore.

**Ho modificato i file ma non vedo i cambiamenti**
Ricarica la pagina forzando lo svuotamento della cache (`Ctrl + F5`).
