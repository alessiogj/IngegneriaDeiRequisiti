# 🖥️ Sistema di Gestione dei Report Accademici
> Progetto di Ingegneria dei Requisiti - Università degli Studi di Verona - A.A. 2023/2024
# Sistema di Gestione Progetti di Ricerca

## Descrizione del Sistema
Il sistema di gestione progetti di ricerca è una piattaforma progettata per supportare ricercatori, responsabili scientifici e amministrativi nella gestione e nel monitoraggio di progetti di ricerca. Il sistema facilita la rendicontazione delle ore di lavoro, la segnalazione delle eventuali deviazioni rispetto alle ore contrattuali, la generazione di report conformi e la gestione delle allocazioni progettuali.

---

## Sommario
1. [Obiettivi del Sistema](#obiettivi-del-sistema)
2. [Salvataggio del Report](#salvataggio-del-report)
3. [Monitoraggio delle Ore](#monitoraggio-delle-ore)
4. [Autenticazione](#autenticazione)
5. [Normativa sulla Privacy](#normativa-sulla-privacy)
6. [Aggiunta di Progetti](#aggiunta-di-progetti)
7. [Aggiunta di Work Package](#aggiunta-di-work-package)
8. [Aggiunta di Task](#aggiunta-di-task)
9. [Modifica delle Milestone](#modifica-delle-milestone)
10. [Controllo delle Milestone](#controllo-delle-milestone)
11. [Notifiche e Avvisi per Report](#notifiche-e-avvisi-per-report)
12. [Aggiunta degli Utenti nel Progetto](#aggiunta-degli-utenti-nel-progetto)
13. [Autori](#autori)

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

## Autori
- [Alessio Gjergji](https://github.com/alessiogj)
- [Valentina Diviggiano](https://github.com/valee001)
- [Stefano Tanfoglio](https://github.com/stetanfoglio)
- [Bozzola Gianluca](https://github.com/gianbo01)
- [Claudio Tinnirello](https://github.com/Tinnyx15)