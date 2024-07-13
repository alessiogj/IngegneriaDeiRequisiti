# 🖥️ Sistema di Gestione dei Report Accademici
> Progetto di Ingegneria dei Requisiti - Università degli Studi di Verona - A.A. 2023/2024
# Sistema di Gestione Progetti di Ricerca

## Descrizione del Sistema
Il sistema di gestione progetti di ricerca è una piattaforma progettata per supportare ricercatori, responsabili scientifici, amministrativi e enti finanziatori nella gestione e monitoraggio di progetti di ricerca. Il sistema facilita la rendicontazione delle ore di lavoro, il monitoraggio delle risorse allocate, la generazione di report conformi alle normative e la gestione delle varie fasi del progetto, assicurando che tutte le parti coinvolte abbiano una visione chiara e aggiornata dello stato di avanzamento del progetto.

## Sommario
- [Entità del Sistema](#entità-del-sistema)
  - [Milestone](#milestone)
  - [Project](#project)
  - [Work Package](#work-package)
  - [Task](#task)
  - [Report](#report)
  - [Admin](#admin)
  - [History](#history)
  - [User](#user)
- [Regole di Business](#regole-di-business)
  - [Inserimento e Modifica dei Progetti](#inserimento-e-modifica-dei-progetti)
  - [Gestione dei Work Package e Task](#gestione-dei-work-package-e-task)
  - [Rendicontazione delle Ore](#rendicontazione-delle-ore)
  - [Generazione dei Report](#generazione-dei-report)
  - [Monitoraggio e Segnalazioni](#monitoraggio-e-segnalazioni)
  - [Gestione Privacy e Accessibilità](#gestione-privacy-e-accessibilità)
- [Permessi](#permessi)
  - [Researcher](#researcher)
  - [Principal Supervisor](#principal-supervisor)
  - [Admin (Permessi)](#admin-permessi)
- [Funzionalità del Sistema](#funzionalità-del-sistema)
  - [Dashboard Progetti](#dashboard-progetti)
  - [Calendario delle Ore](#calendario-delle-ore)
  - [Gestione Report](#gestione-report)
  - [Notifiche e Avvisi](#notifiche-e-avvisi)
  - [Gestione Privacy](#gestione-privacy)
  - [Accessibilità](#accessibilità)
  - [Anagrafica Automatica](#anagrafica-automatica)
- [Glossario](#glossario)

## Entità del Sistema

### Milestone
**Descrizione:** Una milestone rappresenta un evento significativo nel progetto che segna il completamento di un insieme di attività.
- **Fields:**
  - `ID Milestone` (string): Identificativo univoco della milestone.
  - `Nome` (string): Nome descrittivo della milestone.
  - `Data` (date): Data in cui la milestone deve essere raggiunta.
  - `Descrizione` (text): Descrizione della milestone e dei suoi obiettivi.
  - `ID Progetto` (string): Identificativo del progetto a cui la milestone appartiene.
- **Validation Rules:**
  - `Nome` deve essere unico all'interno del progetto.
  - `Data` deve essere specificata e valida.
- **Actions:**
  - **Creazione:** Inserimento di una nuova milestone.
  - **Modifica:** Aggiornamento delle informazioni della milestone.
  - **Eliminazione:** Rimozione della milestone.

### Project
**Descrizione:** Un progetto rappresenta un'iniziativa di ricerca finanziata da un ente. Ogni progetto è suddiviso in work package, che a loro volta contengono diverse attività o task.
- **Fields:**
  - `ID Progetto` (string): Identificativo univoco del progetto.
  - `Nome` (string): Nome descrittivo del progetto.
  - `Data Inizio` (date): Data di inizio del progetto.
  - `Data Fine` (date): Data di fine del progetto.
  - `Descrizione` (text): Descrizione dettagliata degli obiettivi e scopi del progetto.
  - `Ente Finanziatore` (string): Nome dell'ente che finanzia il progetto.
  - `Budget` (float): Budget totale assegnato al progetto, in euro.
  - `Responsabile Amministrativo` (string): Nome del responsabile amministrativo del progetto.
  - `Stato` (enum): Stato attuale del progetto (es. Attivo, Completato, Terminato).
- **Validation Rules:**
  - `Nome` deve essere unico e non nullo.
  - `Data Fine` deve essere successiva alla `Data Inizio`.
  - `Ente Finanziatore` deve essere specificato.
- **Actions:**
  - **Creazione:** Inserimento di un nuovo progetto con tutti i dettagli necessari.
  - **Modifica:** Aggiornamento delle informazioni del progetto, come date, budget, descrizione.
  - **Eliminazione:** Rimozione del progetto (solo se non ci sono work package o task associati).

### Work Package
**Descrizione:** Un work package è una suddivisione del progetto che contiene una serie di attività o task. Ogni work package ha un proprio responsabile scientifico.
- **Fields:**
  - `ID Work Package` (string): Identificativo univoco del work package.
  - `Nome` (string): Nome descrittivo del work package.
  - `Data Inizio` (date): Data di inizio del work package.
  - `Data Fine` (date): Data di fine del work package.
  - `Descrizione` (text): Descrizione dettagliata delle attività e obiettivi del work package.
  - `Risorse Assegnate` (float): Risorse allocate al work package, misurate in mesi-persona e giorni-persona.
  - `Responsabile Scientifico` (string): Nome del responsabile scientifico del work package.
  - `ID Progetto` (string): Identificativo del progetto a cui il work package appartiene.
- **Validation Rules:**
  - `Nome` deve essere unico all'interno del progetto.
  - `Data Fine` deve essere successiva alla `Data Inizio`.
  - `Responsabile Scientifico` deve essere specificato.
- **Actions:**
  - **Creazione:** Inserimento di un nuovo work package.
  - **Modifica:** Aggiornamento delle informazioni del work package.
  - **Eliminazione:** Rimozione del work package (solo se non ci sono task associati).

### Task
**Descrizione:** Un task rappresenta un'unità di lavoro specifica all'interno di un work package, con un obiettivo definito e una durata stabilita.
- **Fields:**
  - `ID Task` (string): Identificativo univoco del task.
  - `Nome` (string): Nome descrittivo del task.
  - `Data Inizio` (date): Data di inizio del task.
  - `Data Fine` (date): Data di fine del task.
  - `Descrizione` (text): Descrizione dettagliata del task e dei suoi obiettivi.
  - `Risorse Assegnate` (float): Risorse allocate al task, misurate in mesi-persona e giorni-persona.
  - `ID Work Package` (string): Identificativo del work package a cui il task appartiene.
- **Validation Rules:**
  - `Nome` deve essere unico all'interno del work package.
  - `Data Fine` deve essere successiva alla `Data Inizio`.
- **Actions:**
  - **Creazione:** Inserimento di un nuovo task.
  - **Modifica:** Aggiornamento delle informazioni del task.
  - **Eliminazione:** Rimozione del task.

### Report
**Descrizione:** Un report è un documento che riepiloga le ore rendicontate e approvate, inviato all’ente finanziatore. I report vengono generati mensilmente e inviati solo se firmati e controfirmati.
- **Fields:**
  - `ID Report` (string): Identificativo univoco del report.
  - `ID Progetto` (string): Identificativo del progetto associato.
  - `Mese` (string): Mese di riferimento del report.
  - `Anno` (string): Anno di riferimento del report.
  - `Ore Totali` (float): Totale delle ore rendicontate nel mese.
  - `Stato` (enum): Stato del report (Inviato, Controfirma Responsabile Scientifico, Controfirma Amministrativo).
- **Validation Rules:**
  - `Mese` deve essere un valore valido (1-12).
  - `Anno` deve essere un valore valido (es. 2024).
  - `ID Progetto` deve essere specificato.
- **Actions:**
  - **Generazione:** Generazione di un nuovo report mensile.
  - **Firma:** Firma del report da parte del ricercatore.
  - **Controfirma:** Approvazione del report da parte del responsabile scientifico e dell’amministrativo.
  - **Invio:** Invio del report all'ente finanziatore.
  - **Conservazione:** Conservazione dei report per 10 anni.

### Admin
**Descrizione:** L'amministrativo è responsabile della gestione dei progetti, work package, task e utenti nel sistema.
- **Fields:**
  - `ID Admin` (string): Identificativo univoco dell'amministrativo.
  - `Nome` (string): Nome dell'amministrativo.
  - `Cognome` (string): Cognome dell'amministrativo.
  - `Email` (string): Email dell'amministrativo.
  - `Ruolo` (enum): Ruolo dell'amministrativo.
- **Validation Rules:**
  - `Email` deve essere univoco e valido.
  - `Ruolo` deve essere amministrativo.
- **Actions:**
  - **Creazione:** Inserimento di un nuovo amministrativo.
  - **Modifica:** Aggiornamento dei dettagli dell'amministrativo.
  - **Eliminazione:** Rimozione dell'amministrativo (solo se non ci sono progetti associati).

### History
**Descrizione:** La storia registra tutte le modifiche e le attività eseguite nel sistema per scopi di audit e monitoraggio.
- **Fields:**
  - `ID History` (string): Identificativo univoco della storia.
  - `Data` (datetime): Data e ora dell'evento.
  - `Utente` (string): Utente che ha eseguito l'azione.
  - `Azione` (string): Descrizione dell'azione eseguita.
  - `Dettagli` (text): Dettagli dell'azione.
- **Validation Rules:**
  - `Data` deve essere specificata e valida.
  - `Utente` deve essere specificato.
  - `Azione` deve essere descrittiva.
- **Actions:**
  - **Creazione:** Registrazione di un nuovo evento nella storia.

### User
**Descrizione:** Gli utenti sono le persone che interagiscono con il sistema, ognuna con un ruolo specifico che determina le operazioni che possono eseguire. Gli utenti possono essere ricercatori o responsabili scientifici.
- **Fields:**
  - `ID Utente` (string): Identificativo univoco dell'utente.
  - `Nome` (string): Nome dell'utente.
  - `Cognome` (string): Cognome dell'utente.
  - `Email` (string): Indirizzo email dell'utente.
  - `Ruolo` (enum): Ruolo dell'utente (Ricercatore, Responsabile Scientifico).
  - `Progetti Associati` (array): Lista dei progetti ai quali l'utente è associato.
- **Validation Rules:**
  - `Email` deve essere univoco e valido.
  - `Ruolo` deve essere uno dei valori predefiniti.
- **Actions:**
  - **Creazione:** Inserimento di un nuovo utente.
  - **Modifica:** Aggiornamento dei dettagli dell'utente.
  - **Eliminazione:** Rimozione dell'utente (solo se non ci sono ore rendicontate associate).

## Regole di Business

### Inserimento e Modifica dei Progetti
**Descrizione:** Solo il responsabile amministrativo può creare e modificare i progetti, includendo dettagli come date di inizio e fine, budget, descrizione, e risorse. Questo garantisce un controllo centralizzato e accurato delle informazioni del progetto.
- **Azioni Permesse:**
  - Creazione di nuovi progetti.
  - Modifica delle informazioni esistenti del progetto.
  - Eliminazione di progetti non attivi e senza work package associati.

### Gestione dei Work Package e Task
**Descrizione:** Ogni work package e task deve avere date di inizio e fine che rispettano le date del progetto. Il responsabile scientifico gestisce il work package e monitora i task, assicurando che le attività siano completate nei tempi previsti.
- **Azioni Permesse:**
  - Creazione di nuovi work package e task.
  - Modifica delle informazioni esistenti di work package e task.
  - Eliminazione di work package e task non attivi e senza ore rendicontate associate.

### Rendicontazione delle Ore
**Descrizione:** I ricercatori possono inserire solo le proprie ore di lavoro, con un massimo di 8 ore giornaliere. Le ore non possono essere rendicontate durante giorni festivi, ferie, o periodi di malattia. Ogni timesheet deve essere firmato dal ricercatore, controfirmato dal responsabile scientifico, e approvato dall’amministrativo.
- **Azioni Permesse:**
  - Inserimento delle ore lavorative giornaliere.
  - Invio dei timesheet per la controfirma.
  - Approvazione dei timesheet da parte del responsabile scientifico e dell’amministrativo.

### Generazione dei Report
**Descrizione:** I report devono essere generati mensilmente e possono essere generati in qualsiasi momento. I report includono una pagina per ogni ricercatore con il dettaglio delle ore giornaliere e mensili. I report devono essere inviati all'ente finanziatore solo dopo essere stati firmati e controfirmati. I report devono essere conservati per 10 anni.
- **Azioni Permesse:**
  - Generazione dei report mensili.
  - Firma e controfirma dei report.
  - Invio dei report all'ente finanziatore.
  - Conservazione dei report per 10 anni.

### Monitoraggio e Segnalazioni
**Descrizione:** Il sistema deve monitorare le ore rendicontate rispetto al budget e alle risorse previste. Deviazioni oltre il 10% devono generare un'alert via email al responsabile scientifico e all’amministrativo. Il sistema deve avvisare se le ore rendicontate superano o sono inferiori rispetto alle ore previste.
- **Azioni Permesse:**
  - Monitoraggio continuo delle ore rendicontate.
  - Generazione di alert per deviazioni.
  - Invio di notifiche via email.

### Gestione Privacy e Accessibilità
**Descrizione:** Gli utenti devono fornire il consenso all’utilizzo dei propri dati per accedere al sistema. Il sistema deve rispettare le normative WCAG per garantire l’accessibilità. I dati devono essere cancellati in caso di revoca del consenso, tranne quelli già consegnati all’ente finanziatore.
- **Azioni Permesse:**
  - Raccolta e registrazione del consenso privacy.
  - Gestione della conformità con le normative WCAG.
  - Cancellazione dei dati in caso di revoca del consenso.

## Permessi

### Researcher
**Descrizione:** Il ricercatore è responsabile dell'inserimento e della gestione delle proprie ore lavorative. Può visualizzare e firmare i propri report.
- **Permessi:**
  - Inserimento delle ore lavorative giornaliere.
  - Firma e invio dei report.
  - Visualizzazione del calendario delle ore rendicontate.

### Principal Supervisor
**Descrizione:** Il responsabile scientifico monitora e controfirma i timesheet dei ricercatori sotto la propria responsabilità e gestisce il work package.
- **Permessi:**
  - Visualizzazione dei timesheet dei ricercatori.
  - Controfirma dei timesheet.
  - Monitoraggio dell’avanzamento delle attività del work package.

### Admin (Permessi)
**Descrizione:** L’amministrativo gestisce l'intero progetto, inclusi work package, task e utenti. È responsabile della gestione dei report e della comunicazione con l'ente finanziatore.
- **Permessi:**
  - Creazione e modifica di progetti, work package e task.
  - Inserimento e gestione degli utenti.
  - Visualizzazione e approvazione dei timesheet.
  - Caricamento dei report nel portale dell’ente finanziatore.
  - Monitoraggio dello stato di avanzamento del progetto e delle risorse.

## Funzionalità del Sistema

### Dashboard Progetti
**Descrizione:** Una dashboard che fornisce una visione d'insieme dello stato di avanzamento dei progetti, delle risorse utilizzate, e delle ore rendicontate.
- **Funzionalità:**
  - Visualizzazione grafica dello stato di avanzamento dei progetti.
  - Monitoraggio del budget e delle risorse allocate.
  - Accesso rapido alle informazioni dei progetti.

### Calendario delle Ore
**Descrizione:** Un calendario che permette di visualizzare le ore rendicontate, le ferie, e le festività nazionali. Supporta diverse visualizzazioni (giornaliera, settimanale, mensile).
- **Funzionalità:**
  - Visualizzazione delle ore lavorative giornaliere.
  - Controllo delle ferie, malattie e festività.
  - Supporto per visualizzazioni in diversi formati temporali.

### Gestione Report
**Descrizione:** Una funzionalità per generare, firmare, controfirmare e inviare report. I report vengono conservati per 10 anni.
- **Funzionalità:**
  - Generazione automatica dei report mensili.
  - Firma digitale e controfirma dei report.
  - Invio dei report all'ente finanziatore.
  - Conservazione dei report per 10 anni.

### Notifiche e Avvisi
**Descrizione:** Un sistema di notifiche che avvisa gli utenti di deviazioni, scadenze e report pronti per la firma.
- **Funzionalità:**
  - Invio di email di avviso per deviazioni oltre il 10%.
  - Notifiche per scadenze imminenti.
  - Avvisi per report pronti per la firma.

### Gestione Privacy
**Descrizione:** Un modulo per raccogliere, registrare e gestire il consenso privacy degli utenti, garantendo la conformità alle normative.
- **Funzionalità:**
  - Raccolta e registrazione del consenso privacy.
  - Gestione della revoca del consenso.
  - Conformità alle normative sulla privacy.

### Accessibilità
**Descrizione:** Il sistema deve rispettare le linee guida WCAG per garantire l’accessibilità del sistema a tutti gli utenti.
- **Funzionalità:**
  - Supporto per daltonici.
  - Testo alternativo per le immagini.
  - Conformità alle linee guida WCAG.

### Anagrafica Automatica
**Descrizione:** Il sistema utilizza l'anagrafica esistente per creare nuovi utenti, gestendo le credenziali con sistemi esterni come GIA o Google.
- **Funzionalità:**
  - Creazione automatica di profili utente.
  - Integrazione con sistemi di gestione delle credenziali esterni.

## Glossario

1. **Milestone:** Evento significativo nel progetto che segna il completamento di un insieme di attività.
2. **Project:** Iniziativa di ricerca finanziata da un ente, composta da vari work package e task.
3. **Work Package:** Sottosezione di un progetto che contiene una serie di attività o task.
4. **Task:** Unità di lavoro specifica all'interno di un work package.
5. **Report:** Documento che riepiloga le ore rendicontate e approvate, inviato all’ente finanziatore.
6. **Admin:** Utente che gestisce i progetti, work package, task, e utenti.
7. **History:** Registro delle modifiche e delle attività eseguite nel sistema.
8. **Researcher:** Utente che inserisce e visualizza le proprie ore lavorative.
9. **Principal Supervisor:** Utente che monitora e controfirma i timesheet dei ricercatori.
10. **Calendar Month:** Rappresenta un mese del calendario per la gestione delle ore lavorative e delle festività.
11. **Calendar Day:** Rappresenta un giorno del calendario per la gestione delle ore lavorative.
12. **User:** Utente generico che può essere un ricercatore o un responsabile scientifico.
---
## Autori
- [Alessio Gjergji](https://github.com/alessiogj)
- [Valentina Diviggiano](https://github.com/valee001)
- [Stefano Tanfoglio](https://github.com/stetanfoglio)
- [Bozzola Gianluca](https://github.com/gianbo01)
- [Claudio Tinnirello]()