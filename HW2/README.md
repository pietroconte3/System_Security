# Homework 2 - Java Cryptography Architecture (JCA)

Questo modulo esplora l'implementazione delle funzioni crittografiche all'interno dell'ecosistema Java, confrontando le librerie native con soluzioni esterne più avanzate.

---

## Traccia dell'Esercitazione (Assignment)

L'obiettivo dell'homework è replicare le operazioni effettuate con OpenSSL utilizzando il linguaggio Java:
* **Gestione Certificati:** Creazione di certificati X.509 e gestione di una catena di certificati completa.
* **Firma Digitale:** Procedure di firma e verifica dell'integrità dei dati.
* **Parsing Certificati:** Estrazione di campi specifici da un certificato (es. Subject, Public Key, Scadenza, Key Usage).

---

## Soluzione Implementata

La soluzione è suddivisa in due progetti Java distinti per mostrare le diverse possibilità del linguaggio:

### Progetto: JavaCryptographyArchitecture
In questo progetto sono state implementate le funzioni di base utilizzando esclusivamente le **funzionalità native della JCA**. 

### Progetto: BouncyCastle
Per le operazioni più complesse (come la generazione avanzata di certificati X.509 v3), è stata utilizzata la libreria **Bouncy Castle**. 
