# Homework 4 - Pay n' Go Next
### Identity Management & Access Control System

**Pay n' Go Next** è un'applicazione web moderna a tre livelli che implementa i più elevati standard di sicurezza enterprise: autenticazione **OAuth 2.0**, controllo degli accessi basato sui ruoli (**RBAC**) e gestione centralizzata dei segreti.

---

## Architettura del Sistema

L'infrastruttura segue un modello **Zero-Trust**, dove ogni comunicazione tra i servizi è protetta da **Mutual TLS (mTLS)** e le credenziali non sono mai salvate in chiaro, grazie all'integrazione con **HashiCorp Vault**.

![Architettura Pay n' Go Next](./pngn_complete.png)

### Componenti Core:
1. **NGINX Reverse Proxy:** Punto di ingresso unico con terminazione TLS e protezione DoS.
2. **Next.js App (PNGN):** Core applicativo con validazione sessioni lato server e CSRF protection.
3. **Keycloak IdP:** Gestore centralizzato di identità, regole e policy di accesso.
4. **PostgreSQL:** Database protetto con Row-Level Security (RLS) e connessioni solo TLS.
5. **HashiCorp Vault:** Il "cuore" della sicurezza. Gestisce la PKI interna e ruota automaticamente i certificati ogni ora.

---

## Sicurezza e Flussi Dati

### Autenticazione e Autorizzazione
Il sistema utilizza il protocollo **OIDC (OpenID Connect)**. L'accesso alle risorse è regolato tramite i gruppi di Keycloak, mappati nel JWT:
* **Registered User:** Profilo personale e storico viaggi.
* **Administrator:** Gestione caselli e configurazione sistema.
* **Account Manager:** Amministrazione degli utenti su Keycloak.

### Gestione dei Segreti (Vault)
Abbiamo implementato un ciclo di vita dei certificati completamente automatizzato:
1. **Vault Agent** si autentica tramite **AppRole**.
2. Richiede un certificato alla **PKI Engine**.
3. Inietta i certificati nel file system del servizio come *read-only*.
4. **Rotazione automatica:** I certificati hanno una durata breve (TTL) e vengono rinnovati ogni ora.
