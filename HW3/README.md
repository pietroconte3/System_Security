# Homework 3 - Configurazione HTTPS Apache/Tomcat

Questo modulo riguarda la configurazione sicura e l'hardening di **Apache HTTP Server** e **Apache Tomcat**, con particolare attenzione all'implementazione del protocollo HTTPS e alla mitigazione delle vulnerabilità note.

---

## Traccia dell'Esercitazione (Assignment)

L'obiettivo dell'homework è mettere in sicurezza l'infrastruttura web attraverso:
* **Certificati HTTPS:** Generazione e gestione dei certificati per la cifratura del traffico.
* **Hardening del Server:** Configurazione sicura di Apache e Tomcat seguendo le *best practices* per eliminare vulnerabilità comuni.
* **Analisi delle Vulnerabilità:** Identificazione e mitigazione dei rischi utilizzando cataloghi pubblici come **MITRE (CVE)**, **CWE** e **OWASP**.

---

## Soluzione Implementata

La soluzione affronta la sicurezza dei server web attraverso analisi statica (**IriusRisk**, **OWASP**) e analisi dinamica (**OWASP ZAP**). Entrambe le implementazioni sono **containerizzate tramite Docker** per garantire isolamento e facilità di deployment.

### Apache HTTP Server
Configurazione focalizzata sulla protezione del perimetro web:
* Supporto **HTTPS/TLS**.
* Implementazione di **Security Headers** (CSP, HSTS, X-Frame-Options).
* Controllo degli accessi e logging avanzato.

### Apache Tomcat
Interventi di hardening specifici per l'application server:
* Gestione remota **JMX criptata**.
* Supporto **HTTPS**.
* Filtri personalizzati per **Content Security Policy** e controllo della cache.
* Disabilitazione delle funzionalità e dei servizi non necessari.
