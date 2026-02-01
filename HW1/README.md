# Homework 1 - OpenSSL

Questo modulo riguarda l'utilizzo pratico della suite **OpenSSL** per la gestione della crittografia simmetrica, asimmetrica e della Public Key Infrastructure (PKI).

---

## Traccia dell'Esercitazione (Assignment)

L'obiettivo dell'homework è completare le seguenti task:
* **Chiavi Simmetriche:** Generazione di chiavi simmetriche e loro utilizzo con diversi algoritmi di cifratura.
* **Chiavi Asimmetriche:** Generazione di coppie di chiavi per la cifratura dei dati, la firma digitale e la firma di certificati.
* **Certificati X.509:** Generazione di certificati conformi allo standard **X.509 v3**.
* **Storage Sicuro:** Salvataggio della chiave privata in formato **PKCS#12 (.p12)** e importazione in un **Java Keystore** tramite l'utility `keytool` (con successiva integrazione in HashiCorp Vault).

---

## Soluzione Implementata

Il lavoro è stato suddiviso in quattro esercizi principali:

### Esercizio 1: Crittografia Simmetrica
Analisi della generazione di chiavi e test di cifratura/decifratura con diversi cifrari a blocchi e modalità di funzionamento.

### Esercizio 2: Crittografia Asimmetrica Diretta
Utilizzo delle chiavi asimmetriche per operazioni di cifratura e decifratura applicate direttamente sul messaggio (non sull'hash), per comprenderne i limiti e il funzionamento.

### Esercizio 3: Trasmissione Sicura dei Messaggi
Implementazione di uno schema completo di trasmissione sicura. Il sistema utilizza algoritmi **simmetrici** per la cifratura del payload e algoritmi **asimmetrici** per lo scambio sicuro delle chiavi e la firma.

### Esercizio 4: Catena di Certificati X.509 v3
Creazione di una gerarchia di certificati completa, simulando una Certification Authority (CA) per il rilascio e la validazione di certificati conformi agli standard moderni.
