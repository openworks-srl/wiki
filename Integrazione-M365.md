# Integrazione OpenLearn con Microsoft 365

## Autenticazione ed aggiornamento anagrafica

> **Note**
> E' necessario disporre di un account amministratore sul Tenant M365 che si intende utilizzare

### 1. Creazione dell'applicazione
1) Entrare sull'interfaccia di amministrazione di Azure AD ([link](https://portal.azure.com/#view/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/~/RegisteredApps))
1) Controllare che il tenant sia corretto
1) Premere su *"Registrazioni App"* dal menù a sinistra
1) Premere su *"Nuova registrazione"*
1) Inserire un nome per la nuova applicazione *(Es. `Openlearn-connector`)*
1) Selezionare la voce *"Account solo in questa directory dell'organizzazione (Solo Default Directory - Tenant singolo)"*
1) Sotto *"URI di reindirizzamento"*, selezionare *"WEB"*
1) Inserire `https://{{url_piattaforma}}/auth/oidc`
1) Premere su *"Registra"*
1) Copiare il valore di *"ID applicazione (client)"* ed inviarlo a  Openworks.

### 2. Assegnazzione permessi

1) Premere su *" Autorizzazioni API"* dal menu a sinistra
1) Premere su *"Aggiungi un'autorizzazione"*
1) Selezionare *"Microsoft Graph"*
1) Selezionare *"Autorizzazioni applicazione"*
1) Cercare nella barra di ricerca, quindi selezionare, i seguenti permesi:
    - *Domain.ReadWrite.All*
    - *User.ReadWrite.All* (sotto *"user"*, NON *"IdentityRiskyUser"*)
    - *Directory.ReadWrite.All*
1) Nella parte alta dello schermo (a destra) selezionare *"Autorizzazioni delegate"*
1) Cercare nella barra di ricerca, quindi selezionare, i seguenti permesi:
    - *User.Read*
    - *User.ReadWrite.All*
    - *Directory.AccessAsUser.All*
    - *Directory.ReadWrite.All*
1) Premere su *"Aggiungi autorizzazioni"*

### 3. Generazione chiave

1) Premere su *"Certificati e segreti"* dal menù a sinistra
1) Premere su *"Nuovo segreto client"*
1) Immettere una descrizione (Es. `Chiave generata il {{data_odierna}}`)
1) Selezionare *"730 giorni (24 mesi)"* come scadenza
1) Premere su *"Aggiungi"*
1) Copiare immediatamente il *Valore* della chiave appena generata ed inviarla ad Openworks (**Attenzione, la chiave non sarà mai più visibile una volta lasciata la pagina!**)

### 4. Autorizzazione applicazione

> **Note**
> Riceverai da Openworks delle credenziali temporanee per l'accesso a Openlearn da utilizzare durante la procedura


1) Recarsi al seguente indirizzo: [Admin consent](https://{{url_piattaforma}}/local/o365/acp.php?mode=adminconsent)
1) Assicurarsi che il browser che si sta utilizzando sia attualmente autenticato con l'account Microsoft amministratore usato nei passsaggi precedenti
1) Accedere alla piattaforma *"{{url_piattaforma}}"* utilizzando le credenziali fornite da Openworks
1) Apparirà una finestra di autorizzazione di Microsoft, controllare i permessi e premere su *"xxx"*
1) Recarsi all'indirizzo [{{url_piattaforma}}](https://{{url_piattaforma}})
1) Premere sull'icona di profilo in alto a destra, e selezionare *"Esci"* per disconnettere l'account temporaneo

### 4. Test dell'integrazione

1) Utilizzando un browser in modalità "in incognito/anonimo", recarsi all'indirizzo [{{url_piattaforma}}](https://{{url_piattaforma}}/auth/oidc})
1) Entrare con le proprie credenziali Microsoft, se l'integrazione funziona si verrà reindirizzati alla piattaforma Openlearn.

