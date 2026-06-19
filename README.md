# SteamDeck_Regia_ITA
SteamDeck Regia è una soluzione di controllo remoto pensata per gestire una Steam Deck da un PC tramite browser web, senza dover installare client pesanti sul computer di controllo.

Il progetto è composto da:

- **Backend Node.js** (server centrale)
- **Agent Python** installato sulla Steam Deck
- **Interfaccia Web** accessibile da browser

## Funzionalità principali

### Controllo remoto della Steam Deck
- Controllo del mouse
- Click sinistro, destro e centrale
- Invio tasti e scorciatoie da tastiera
- Digitazione automatica di testo
- Supporto layout tastiera italiano
- Simulazione input tramite X11/XTest

### Streaming video in tempo reale
- Visualizzazione dello schermo della Steam Deck direttamente dal browser
- Trasmissione frame tramite WebSocket
- Bassa latenza per utilizzo remoto

### Streaming audio
- Trasmissione audio dalla Steam Deck al browser
- Riproduzione in tempo reale durante la sessione remota

### Gestione file
- Caricamento file verso la Steam Deck
- Trasferimento rapido tramite interfaccia web
- Ideale per ROM, giochi, mod, configurazioni e documenti

### Gestione sistema
- Esecuzione di comandi remoti
- Operazioni amministrative
- Salvataggio password sudo
- Raccolta log diagnostici

### Rilevamento automatico dispositivi
- Individuazione automatica delle Steam Deck collegate
- Stato online/offline
- Gestione delle connessioni attive

### Sicurezza
- Token di autenticazione generato automaticamente
- Protezione delle API tramite header dedicato
- Persistenza del token tra i riavvii

---

## Architettura

```text
┌───────────────┐
│ Browser Web   │
└───────┬───────┘
        │
        ▼
┌─────────────────────┐
│ Backend Node.js     │
│ Express + WebSocket │
└───────┬─────────────┘
        │
        ▼
┌─────────────────────┐
│ Agent Python        │
│ Steam Deck          │
└─────────────────────┘
```

Il backend funge da ponte tra il browser e l'agente installato sulla Steam Deck.

---

## Componenti principali

### Backend
Tecnologie utilizzate:

- Node.js
- Express
- WebSocket
- Multer
- CORS

Responsabilità:

- Gestione API
- Autenticazione
- Streaming video/audio
- Gestione upload
- Coordinamento agenti

### Agent Steam Deck
Tecnologie utilizzate:

- Python 3
- X11
- XTest
- Threading
- Utility Linux

Responsabilità:

- Acquisizione schermo
- Invio audio
- Simulazione input
- Gestione sistema operativo
- Comunicazione con il backend

---

## Casi d'uso

- Controllare la Steam Deck da un PC Windows
- Utilizzare la modalità Desktop da remoto
- Installare mod e file senza collegare periferiche
- Gestire launcher e applicazioni
- Assistenza remota a una Steam Deck
- Trasferimento rapido di file in rete locale
- Controllo da tablet o smartphone tramite browser

---

## Funzionalità sperimentali

A seconda della versione del progetto possono essere presenti:

- Installazione automatica componenti
- Integrazione clipboard condivisa
- Supporto gamepad virtuale
- Gestione Proton-GE
- Automazioni dedicate alla Steam Deck

---

## Requisiti

### Server
- Node.js 18+
- Rete locale o accesso remoto configurato

### Steam Deck
- SteamOS
- Python 3
- Accesso Desktop Mode
- 
### Licenza
Copyright (c) 2026 SteamDeck Regia Contributors

SteamDeck Regia is provided free of charge.

Permission is granted to use, copy and modify this software for personal and non-commercial purposes only.

Commercial use, resale, sublicensing, hosting as a paid service, or inclusion in commercial products is strictly prohibited without prior written permission from the author.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND.

---

## Stato del progetto

Progetto in sviluppo continuo.
Le funzionalità possono evolvere e cambiare tra le varie versioni.

