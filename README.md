# 🖥️ Sistema di Gestione dei Report Accademici
> Progetto di Ingegneria dei Requisiti - Università degli Studi di Verona - A.A. 2023/2024

## Descrizione del Sistema
Il sistema di gestione progetti di ricerca è una piattaforma progettata per supportare ricercatori, responsabili scientifici e amministrativi nella gestione e nel monitoraggio di progetti di ricerca. Il sistema facilita la rendicontazione delle ore di lavoro, la segnalazione delle eventuali deviazioni rispetto alle ore contrattuali, la generazione di report conformi e la gestione delle allocazioni progettuali.

---

## Sommario
- [Glossario](#glossario)
- [Obiettivi del Sistema](#obiettivi-del-sistema)
    - [Salvataggio del Report](#salvataggio-del-report)
    - [Monitoraggio delle Ore](#monitoraggio-delle-ore)
    - [Autenticazione](#autenticazione)
    - [Normativa sulla Privacy](#normativa-sulla-privacy)
    - [Aggiunta di Progetti](#aggiunta-di-progetti)
    - [Aggiunta di Work Package](#aggiunta-di-work-package)
    - [Aggiunta di Task](#aggiunta-di-task)
    - [Modifica delle Milestone](#modifica-delle-milestone)
    - [Controllo delle Milestone](#controllo-delle-milestone)
    - [Notifiche e Avvisi per Report](#notifiche-e-avvisi-per-report)
    - [Aggiunta degli Utenti nel Progetto](#aggiunta-degli-utenti-nel-progetto)
- [Requisiti Non Funzionali](#requisiti-non-funzionali)
- [Autori](#autori)

---

## Glossario
- **Ricercatore**: Utente che partecipa attivamente al progetto di ricerca eseguendo compiti specifici.
- **Responsabile Scientifico**: Utente che sovrintende la gestione scientifica e tecnica del progetto.
- **Amministrativo**: Utente che gestisce gli aspetti amministrativi e organizzativi del progetto.
- **Work Package**: Un'unità di lavoro all'interno di un progetto che contiene uno o più task.
- **Task**: Una singola attività all'interno di un work package.
- **Milestone**: Un punto di controllo nel progetto che indica il completamento di una fase o attività significativa.
- **Report**: Documento che riporta i risultati, la rendicontazione oraria e le attività svolte durante il progetto di ricerca.
- **Deviazione**: Differenza tra le ore lavorative effettuate e le ore contrattuali.
- **Alert**: Notifica visiva che segnala una deviazione rispetto alle ore contrattuali.
- **Backup**: Copia di sicurezza dei dati per garantire la disponibilità e l'integrità dei dati.
- **Firma Digitale**: Firma elettronica che garantisce l'autenticità e l'integrità del documento.
- **Controfirma**: Firma elettronica che attesta l'approvazione del documento.
- **Consenso**: Autorizzazione dell'utente al trattamento dei dati personali.
- **Autorizzazione**: Permesso dell'utente per accedere a determinate funzionalità del sistema.
---

## Obiettivi del Sistema
Il sistema di gestione progetti di ricerca è progettato per automatizzare e semplificare il processo di gestione dei progetti di ricerca, dalla creazione dei progetti alla generazione dei report. Il sistema deve garantire la conformità alle normative sulla privacy, fornendo un'interfaccia intuitiva e facile da usare per gli utenti.

Il sistema deve supportare le seguenti funzionalità principali:
- Creazione e gestione di progetti, work package e task.
- Rendicontazione delle ore lavorative.
- Generazione e mantenimento di report conformi alle normative.
- Gestione delle notifiche e degli avvisi.
- Gestione dei permessi e delle autorizzazioni per l'accesso alle varie funzionalità.

---

### Salvataggio del Report
Il sistema deve garantire che i report siano mantenuti per un periodo di 10 anni, in conformità con le normative sulla conservazione dei documenti. Deve essere fornita un'interfaccia per mantenere i report completi di firma digitale e controfirma, una volta che sono stati approvati.

Per garantire che i report siano conservati in modo sicuro e conforme alle normative sulla privacy, il sistema deve implementare un backup automatico dei dati e un sistema di recupero dei dati in caso di perdita o danneggiamento.

---

### Monitoraggio delle Ore
Il sistema deve monitorare le ore di ciascun ricercatore rispetto alle ore indicate nel contratto. Devono essere identificate e segnalate le seguenti categorie di deviazione:
- **Deviazione sotto al 5%:** Alert segnalato in verde all'interno dell'applicativo.
- **Deviazione tra il 5% e il 10%:** Alert segnalato in arancione all'interno dell'applicativo.
- **Deviazione sopra al 10%:** Alert segnalato in rosso all'interno dell'applicativo.

---

### Autenticazione
Se l'utente non è autenticato, il sistema deve reindirizzarlo alla pagina di login. La gestione delle credenziali di accesso è delegata all'amministrativo.

In caso di smarrimento delle credenziali di accesso, l'utente deve poter richiedere il ripristino della password tramite un processo sicuro.

---

### Normativa sulla Privacy
Il sistema deve garantire la conformità alle normative sulla privacy, assicurando che i dati personali degli utenti siano protetti e trattati in modo sicuro. Deve essere fornita un'interfaccia per la gestione dei consensi e delle autorizzazioni.

Gli utenti devono accettare la normativa sulla privacy al primo accesso al sistema; in caso contrario, non potranno accedere all'applicativo.

---

### Aggiunta di Progetti
Il sistema deve consentire all'amministrativo di aggiungere nuovi progetti. L'aggiunta di un nuovo progetto richiede la presenza di un responsabile scientifico, che sovrintenderà la gestione del progetto.

---

### Aggiunta di Work Package
Il sistema deve consentire al responsabile scientifico di aggiungere nuovi work package. Non è richiesta l'approvazione dell'amministrativo per questa operazione. Il responsabile scientifico ha piena libertà nella gestione dei work package. La creazione di un nuovo work package non richiede la presenza dei ricercatori.

---

### Aggiunta di Task
Il sistema deve consentire al responsabile scientifico di aggiungere nuovi task. Non è richiesta l'approvazione dell'amministrativo per questa operazione. Il responsabile scientifico ha piena libertà nella gestione dei task. La creazione di un nuovo task richiede la presenza di almeno un ricercatore.

---

### Modifica delle Milestone
Il sistema deve consentire al responsabile scientifico di modificare le milestone. Se i tempi di consegna non vengono rispettati, il responsabile scientifico può ritardare la milestone, spostando le consegne in avanti. In tal caso, il contenuto della milestone deve essere riportato alla milestone successiva.

---

### Controllo delle Milestone
Il sistema deve consentire al responsabile scientifico di controllare lo stato di avanzamento delle milestone. Il responsabile scientifico può verificare se le milestone sono state completate entro i tempi previsti e se le scadenze sono state rispettate.

---

### Notifiche e Avvisi per Report
Il sistema deve fornire un sistema di notifiche e avvisi per informare gli utenti di eventuali errori o problemi di rete nell'invio del report all'amministrativo.

---

### Aggiunta degli Utenti nel Progetto
L'amministrativo deve poter aggiungere nuovi utenti ai progetti. L'amministrativo può assegnare ruoli diversi agli utenti, come ricercatore o responsabile scientifico, in base alle necessità del progetto.

---

## Requisiti Non Funzionali
1. **Prestazioni**: Il sistema deve supportare almeno 100 utenti simultanei senza degrado delle prestazioni.
2. **Scalabilità**: Deve essere possibile scalare il sistema per supportare un numero maggiore di utenti e progetti senza necessità di significative modifiche architetturali.
3. **Sicurezza**: Tutti i dati devono essere crittografati sia a riposo che in transito. L'accesso al sistema deve essere controllato tramite autenticazione a due fattori.
4. **Affidabilità**: Il sistema deve garantire un uptime del 99.9%, con sistemi di backup e ripristino dei dati in caso di guasto.

---

## Regole di Business
1. **Creazione di Progetti**: Solo l'amministrativo può creare nuovi progetti. Un progetto deve avere un responsabile scientifico assegnato.
2. **Gestione dei Work Package**: Il responsabile scientifico può aggiungere e gestire i work package senza necessità di approvazione amministrativa.
3. **Aggiunta di Task**: Il responsabile scientifico può aggiungere task che richiedono la presenza di almeno un ricercatore.
4. **Modifica delle Milestone**: Il responsabile scientifico può modificare le milestone in caso di ritardo, riportando il contenuto alla milestone successiva.
5. **Rendicontazione delle Ore**: Il sistema deve monitorare le ore lavorative e segnalare le deviazioni rispetto alle ore contrattuali.
6. **Generazione di Report**: Il sistema deve generare report completi di firma digitale e conservarli per 10 anni.
7. **Gestione degli Utenti**: L'amministrativo può aggiungere nuovi utenti e assegnare ruoli specifici (ricercatore o responsabile scientifico).

---

## Permessi
- **Creazione Progetti**: Amministrativo
- **Lettura Progetti**: Amministrativo, Responsabile Scientifico, Ricercatore
- **Modifica Progetti**: Amministrativo, Responsabile Scientifico
- **Cancellazione Progetti**: Amministrativo
- **Creazione Work Package**: Responsabile Scientifico
- **Lettura Work Package**: Amministrativo, Responsabile Scientifico, Ricercatore
- **Modifica Work Package**: Responsabile Scientifico
- **Cancellazione Work Package**: Responsabile Scientifico
- **Creazione Task**: Responsabile Scientifico
- **Lettura Task**: Amministrativo, Responsabile Scientifico, Ricercatore
- **Modifica Task**: Responsabile Scientifico
- **Cancellazione Task**: Responsabile Scientifico
- **Modifica Milestone**: Responsabile Scientifico
- **Lettura Milestone**: Amministrativo, Responsabile Scientifico, Ricercatore
- **Creazione Report**: Amministrativo, Responsabile Scientifico
- **Lettura Report**: Amministrativo, Responsabile Scientifico, Ricercatore
- **Modifica Report**: Amministrativo, Responsabile Scientifico
- **Cancellazione Report**: Amministrativo
- **Creazione Utenti**: Amministrativo
- **Lettura Utenti**: Amministrativo, Responsabile Scientifico
- **Modifica Utenti**: Amministrativo
- **Cancellazione Utenti**: Amministrativo

---

## Autori
- [Alessio Gjergji](https://github.com/alessiogj)
- [Valentina Diviggiano](https://github.com/valee001)
- [Stefano Tanfoglio](https://github.com/stetanfoglio)
- [Bozzola Gianluca](https://github.com/gianbo01)
- [Claudio Tinnirello](https://github.com/Tinnyx15)