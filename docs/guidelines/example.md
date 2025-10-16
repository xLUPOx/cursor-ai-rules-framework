# Esempio di Guideline

Questo è un esempio di linea guida per la gestione sia dei **task** che delle **feature**.

## Convenzione di Nominazione dei File
- **Task:** `[data]-[nome-funzionalità]-task.md`  
  Esempio: `2025-10-16-user-authentication-task.md`
- **Feature:** I file di guideline specifici per funzionalità si trovano in `docs/active/features/[nome-funzionalità]/`

## Conformità allo Stile
Tutti i task e le feature devono rispettare:
1. **Stile di Codifica:** `docs/guidelines/project_coding_style_analysis.json`
2. **Linee Guida della Funzionalità:** `docs/active/features/[nome-funzionalità]/`
3. **Template Selezionati dall’Utente:** `docs/templates/corporate/` oppure `docs/templates/startup/`

## Struttura dei Commit
Ogni commit deve includere:
- **Conformità allo Stile:** convenzioni di naming, gestione errori e framework di testing dal JSON di progetto
- **Conformità ai Template:** rispetto delle linee guida dei template scelti
- **Verifica:** test eseguiti con il framework stabilito e log secondo il formato richiesto dal progetto
