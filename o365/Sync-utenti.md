# Sincronizzazione anagrafica con Microsoft Active Directory
Il processo funziona in automatico e gira ogni notte, sincronizzando tutti gli utenti che rispettano le opzioni di restrzione impostate, è possibile sincronizzare qualsiasi campo presente sull'AD all'interno della piattaforma.

## Quali utenti vengono sincronizzati
Normalmente vengono importati e sincronizzati tutti gli utenti presenti sull'AD, è possibile decidere di importare solo alcuni utenti, utilizzando le opzioni di restrzione.

### Utenti già esistenti
E' possibile impostare il processo di sincronizzazione per eseguire il matching tra gli utenti esistenti e quelli presenti sull'AD. {{#ow}}Utilizzando l'opzione ` Trova corrispondenza tra utenti Moodle preesistenti e account con lo stesso nome in Azure AD
` all'interno del tab `Sync setting` del plugin `local_365`{{/ow}}
Gli utenti già esistenti sulla piattaforma (se presenti) verranno sincronizzati tramite il campo `Username` o `Email` sulla piattaforma Openlearn ed il campo `UPN` sull'AD microsoft.
E' possibile selezionare quale campo della piattaforma utilizzare per il mathcing.

### Come restringere le utenze sincronizzate

## Cosa è possibile sincronizzare
