# Manuale Super Semplice: Git & GitHub

Benvenuto in questo manuale pratico! Questa guida è pensata per farti muovere i primi passi senza complicazioni, dandoti solo i concetti necessari e una procedura **passo passo** per creare il tuo primo progetto e caricarlo online.

---

## 1. La Differenza in Parole Povere

- **Git**: È un programma installato sul tuo computer. Funziona come una "macchina del tempo" o una "salvataggio dei dati" per i tuoi file di testo e codice. Ti permette di salvare degli "screenshot" del tuo progetto nel tempo per poter tornare indietro se fai errori.
- **GitHub**: È un sito web (un servizio online) che ospita i tuoi progetti Git nel cloud. Ti permette di conservare un backup online, mostrare il tuo lavoro agli altri e collaborare.

> **Analogia**: Git è come il programma *Microsoft Word* sul tuo computer, mentre GitHub è come *Google Drive* dove carichi il file word salvato per condividerlo.

---

## 2. Termini Chiave (I 5 pilastri)

1. **Repository (o "Repo")**: La cartella del tuo progetto gestita da Git.
2. **Commit**: Un "salvataggio" formale del progetto. Ogni volta che fai un commit, crei un punto di ripristino con un messaggio descrittivo.
3. **Stage / Index**: La zona d'attesa. Prima di confermare un salvataggio (commit), scegli quali file modificati mettere nella zona d'attesa.
4. **Remote**: Il link tra la tua cartella locale sul PC e il repository online su GitHub.
5. **Push**: L'operazione con cui "spingi" i tuoi salvataggi locali (commit) su GitHub online.

---

## 3. Preparazione Iniziale (Da fare una sola volta)

### A. Installa Git
Se non l'hai già fatto, scarica e installa Git dal sito ufficiale ([git-scm.com](https://git-scm.com/)).

### B. Configura il tuo nome ed email
Apri il Terminale (Mac/Linux) o **Git Bash / Prompt dei Comandi** (Windows) ed esegui questi due comandi (sostituendo i tuoi dati):

```bash
git config --global user.name "Il Tuo Nome"
git config --global user.email "la_tua_email@esempio.com"
```

### C. Crea un account su GitHub
Se non ne hai uno, registrati gratuitamente su [GitHub.com](https://github.com/).

---

## 4. Tutorial Passo Passo: Il Tuo Primo Progetto (da PC a GitHub)

Segui questi passaggi nell'ordine esatto per completare il tuo primo flusso di lavoro.

---

### PASSO 1: Crea una cartella sul tuo computer
Apri il terminale (o la riga di comando) e crea una nuova cartella per il tuo progetto, poi entracci dentro:

```bash
mkdir mio-primo-progetto
cd mio-primo-progetto
```

---

### PASSO 2: Inizializza Git nella cartella
Dice a Git di iniziare a monitorare questa cartella.

```bash
git init
```

*Cosa succede:* Git crea una cartella nascosta `.git` all'interno del tuo progetto per salvare lo storico delle modifiche.

---

### PASSO 3: Crea un file e fai il tuo primo salvataggio (Commit)

1. Crea un semplice file di testo (ad esempio `README.md`):

```bash
echo "# Il mio primo progetto Git" > README.md
```

2. Verifica lo stato del progetto:

```bash
git status
```
*(Vedrai il file `README.md` evidenziato in rosso: significa che Git ha notato la presenza del file ma non lo sta ancora tracciando).*

3. Aggiungi il file alla **zona d'attesa** (Staging area):

```bash
git add README.md
```
*(Puoi anche usare `git add .` per aggiungere tutti i file modificati contemporaneamente).*

4. Fai il tuo primo **Commit** (salvataggio):

```bash
git commit -m "Primo salvataggio: aggiunto il file README"
```

---

### PASSO 4: Crea il Repository su GitHub

1. Vai su [GitHub.com](https://github.com/) e fai l'accesso.
2. In alto a destra, clicca sul pulsante **"+"** e seleziona **New repository**.
3. Compila solo questi due campi:
   - **Repository name**: `mio-primo-progetto`
   - Lascia la visibilità su **Public** (o Private se preferisci).
   - **IMPORTANTE**: Non spuntare "Add a README file", "Add .gitignore" o licenze (il repository su GitHub deve essere completamente vuoto).
4. Clicca sul pulsante verde **Create repository**.

---

### PASSO 5: Collega la cartella locale a GitHub

Dopo aver creato il repository, GitHub ti mostrerà una pagina con delle istruzioni. Cerca la sezione che dice **"…or push an existing repository from the command line"**.

Copia ed esegui i comandi indicati direttamente nel tuo terminale. Assomiglieranno a questi:

```bash
# 1. Rinomina il ramo principale in 'main' (standard moderno)
git branch -M main

# 2. Collega il tuo Git locale all'indirizzo di GitHub
git remote add origin https://github.com/TUO-USERNAME/mio-primo-progetto.git

# 3. Invia i tuoi file online
git push -u origin main
```

*(Sostituisci `TUO-USERNAME` con il tuo vero nome utente su GitHub).*

> **Nota di autenticazione**: La prima volta che fai il `push`, il terminale o una finestra pop-up ti chiederà di autenticarti con le tue credenziali GitHub.

---

### PASSO 6: Verifica su GitHub!
Ricarica la pagina del tuo repository su GitHub nel browser. Troverai il tuo file `README.md` visibile online!

---

## 5. Il Flusso di Lavoro Quotidiano (Cheat Sheet)

D'ora in poi, ogni volta che modifichi i tuoi file e vuoi salvare le novità sia sul PC che su GitHub, ti basterà eseguire solo questi tre comandi:

```bash
# 1. Aggiungi tutte le modifiche alla zona d'attesa
git add .

# 2. Crea un punto di salvataggio con una descrizione
git commit -m "Descrizione di cosa hai modificato o aggiunto"

# 3. Spingi i cambiamenti su GitHub
git push
```

### Un piccolo comando extra utilissimo
Se stai lavorando da un altro PC o hai modificato file direttamente da GitHub e vuoi scaricare le ultime novità sul tuo computer:

```bash
git pull
```