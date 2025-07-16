# Claude Code: Guida Italiana

Una collezione di tecniche e strategie per utilizzare Claude Code in modo efficace. Basata su esperienza pratica di sviluppo quotidiano.

## Introduzione

Claude Code è uno strumento potente per lo sviluppo assistito da AI. Questa guida raccoglie le tecniche più efficaci per massimizzarne l'utilizzo, ridurre i bug e migliorare la produttività.

## Installazione

### Prerequisiti

- Account Claude attivo
- Cursor AI installato

### Setup per Sistema Operativo

#### macOS
```bash
# Installa Cursor AI
curl -fsSL https://cursor.sh/install.sh | sh
```

#### Windows
Scarica l'installer da [cursor.sh](https://cursor.sh) ed esegui il file `.exe`.

#### Linux
```bash
# Ubuntu/Debian
curl -fsSL https://cursor.sh/install.sh | sh

# Arch Linux
yay -S cursor-bin

# Verifica installazione
cursor --version
```

### Configurazione in Cursor

1. Apri **Settings** → **Extensions**
2. Cerca e installa **Claude Code**
3. Configura le tue credenziali API nelle impostazioni

## Configurazione

### Il File claude.md

Crea un file `claude.md` nella root del progetto. Questo file viene letto automaticamente da Claude Code ad ogni prompt.

```markdown
# Regole di Sviluppo

## Comportamento
- Dividi ogni task in micro-operazioni
- Chiedi conferma prima di procedere
- Documenta ogni decisione importante

## Codice
- Usa nomenclatura chiara e consistente
- Includi commenti per logiche complesse
- Ottimizza per leggibilità e performance

## Sicurezza
- Mai secrets nel frontend
- Valida tutti gli input
- Implementa proper error handling
```

### Variabili d'Ambiente

```bash
# .env.example
CLAUDE_API_KEY=your_key_here
DATABASE_URL=your_database_url
```

## Modalità Plan

La modalità Plan permette di pianificare il lavoro prima dell'esecuzione. È particolarmente utile per task complessi.

### Attivazione

Attiva la modalità Plan con uno di questi metodi:

```bash
# Shortcut tastiera
Shift + Tab + Tab

# Comando esplicito
/plan
```

### Strategia dei Modelli

Per ottimizzare costi e qualità, usa modelli diversi per fasi diverse:

```bash
# Per la pianificazione (massima precisione)
/mod opus

# Per l'esecuzione (velocità + risparmio)
/mod sonnet
```

### Esempio Pratico

```markdown
# Input in Plan Mode
"Creo una API REST per gestione utenti con:
- Autenticazione JWT
- CRUD operazioni
- Validation middleware
- Rate limiting
- Documentazione OpenAPI"
```

Claude risponderà con un piano dettagliato step-by-step che potrai approvare prima dell'esecuzione.

## Gestione del Contesto

### Comando /clear

Usa `/clear` per pulire il contesto quando:
- Completi un task importante
- Cambi argomento o funzionalità
- Noti risposte inconsistenti
- Dopo 30-45 minuti di lavoro continuo

```bash
# Pulisci il contesto
/clear
```

### Indicatori per Clearing

**Segnali che è tempo di /clear:**
- Risposte sempre più lunghe
- Ripetizioni di codice
- Riferimenti a task obsoleti
- Confusione sui requirements

## Utilizzo delle Immagini

Claude Code può analizzare screenshot per comprendere design e debug visuale.

### Screenshot

| OS | Shortcut |
|---|---|
| macOS | `Cmd + Shift + 4` |
| Windows | `Win + Shift + S` |
| Linux | `Ctrl + Shift + Print` |

### Casi d'Uso

#### Design Inspiration
```markdown
"Analizza questo design di [app] e crea un componente simile 
usando React e Tailwind CSS"
```

#### Debug Visuale
```markdown
"Questo layout non funziona correttamente. Basandoti sullo 
screenshot, system il CSS per centrare gli elementi"
```

## Sicurezza

### Security Check

Dopo ogni feature, esegui un controllo di sicurezza:

```markdown
"Analizza il codice per vulnerabilità di sicurezza:
- API keys nel frontend
- SQL injection
- XSS vulnerabilities  
- Input validation
- Error handling sicuro"
```

### Checklist di Sicurezza

- [ ] Secrets solo nel backend/env
- [ ] Input validation su tutti i campi
- [ ] Password hashate (bcrypt)
- [ ] HTTPS configurato
- [ ] CORS impostato correttamente
- [ ] Rate limiting attivo
- [ ] Logging senza dati sensibili

## Workflow di Sviluppo

### Ciclo Completo

1. **Plan**: Attiva Plan Mode e definisci obiettivi
2. **Execute**: Usa Sonnet per implementazione
3. **Secure**: Controlla vulnerabilità
4. **Commit**: Salva su Git
5. **Clear**: Pulisci contesto
6. **Repeat**: Prossima funzionalità

### Git Integration

```bash
# Setup iniziale
git init
git add .
git commit -m "🎉 Initial commit"

# Workflow quotidiano
git add .
git commit -m "✨ Add: [feature description]"
git push
```

### Convenzioni Commit

| Tipo | Emoji | Descrizione |
|---|---|---|
| Feature | ✨ | Nuove funzionalità |
| Fix | 🐛 | Correzione bug |
| Refactor | ♻️ | Refactoring codice |
| Docs | 📝 | Aggiornamenti documentazione |
| Style | 🎨 | Modifiche UI/styling |

## Apprendimento

### Learning Prompt

Dopo aver completato una feature, usa questo prompt per comprendere il codice:

```markdown
"Spiegami il codice come se fossi un mentor esperto:
- Cosa fa ogni funzione principale
- Perché hai scelto questo approccio
- Come fluiscono i dati
- Pattern di design utilizzati
- Possibili miglioramenti futuri"
```

### Progressione

1. **Copy-Paste**: Usa il codice generato così com'è
2. **Comprensione**: Capisci cosa fa il codice
3. **Modifica**: Piccoli aggiustamenti autonomi
4. **Creazione**: Sviluppo indipendente

## Ottimizzazione della Produttività

### Chat Produttiva

Durante i tempi di attesa di Claude Code, usa una chat separata per:

```markdown
"Aiutami a restare produttivo durante le pause:
- Brainstorming nuove features
- Pianificazione architettura
- Idee per miglioramenti
- Strategia di business"
```

### Evita Distrazioni

**Vietato durante le pause:**
- Social media
- Video casuali
- News browsing

**Permesso:**
- Pianificazione progetto
- Research tecnico
- Documentazione

## Esempi Pratici

### Todo App con React

```markdown
# Plan Mode Input
"Creare todo app con:
- React + TypeScript
- Local storage persistence
- Filtri per stato
- Dark mode toggle
- Responsive design"
```

**Risultato**: Piano dettagliato con 8-10 step verificabili.

### API REST con Node.js

```markdown
# Plan Mode Input  
"API REST per blog con:
- Express + MongoDB
- Autenticazione JWT
- CRUD posts e users
- Middleware validation
- Error handling
- API documentation"
```

**Risultato**: Architettura completa con security best practices.

## Troubleshooting

### Problemi Comuni

**Claude non risponde correttamente**
- Usa `/clear` per pulire contesto
- Sii più specifico nei prompt
- Verifica configurazione API

**Codice con bug frequenti**
- Assicurati di avere `claude.md` configurato
- Usa sempre Plan Mode per task complessi
- Implementa security check regolari

**Costi elevati**
- Usa strategia Opus/Sonnet
- Applica `/clear` più frequentemente
- Ottimizza la lunghezza dei prompt

## FAQ

### Claude Code funziona con tutti i linguaggi?

**Ottimo supporto:**
- JavaScript/TypeScript
- Python
- React/Vue/Angular
- Node.js
- HTML/CSS

**Supporto limitato:**
- Mobile nativo (Swift/Kotlin)
- Low-level languages (C++/Rust)

### Quanto costa utilizzare Claude Code?

**Piani disponibili:**
- **Free**: 10 messaggi/giorno
- **Pro ($20/mese)**: 100 messaggi/giorno  
- **Team ($25/mese)**: 500 messaggi/giorno

Con le tecniche di ottimizzazione, il risparmio può essere del 50-70%.

### È sicuro per progetti commerciali?

Sì, seguendo le best practices di sicurezza:
- Security check regolari
- Mai dati sensibili nei prompt
- Code review umano
- Rispetto delle policy aziendali

## Contributing

Questa guida è open source. Per contribuire:

1. Fork il repository
2. Crea un branch per la feature
3. Implementa le modifiche
4. Apri una Pull Request

### Tipi di Contributi

- Nuove tecniche testate
- Correzioni e miglioramenti
- Esempi pratici
- Traduzioni

## Licenza

MIT License - Vedi file `LICENSE` per dettagli.

## Crediti

**Autore**: Francesco Mancino  
**Ubicazione**: Roma, Italia  
**Contatto**: mancino22@gmail.com

**Link utili:**
- [LinkedIn](https://www.linkedin.com/in/francesco-mancino-dev/)
- [Twitter](https://twitter.com/freshgr4m)
- [GitHub Issues](https://github.com/freshgr4m/claude-code-pro/issues)

---

*Ultima modifica: Gennaio 2025*
