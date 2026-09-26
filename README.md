# Progressì

Demo interattiva di un SaaS di performance intelligence per Personal Trainer, palestre e atleti. L'obiettivo è validare un'esperienza in cui l'atleta registra ogni serie con pochissimo attrito e il coach identifica in pochi secondi progressi, plateau e criticità.

## Funzionalità demo

- Landing con accesso immediato alle modalità Atleta e Personal Trainer
- Onboarding iniziale in 3 step con agenda, insight e allenamento guidato
- Workout mobile-first con valori precompilati, stepper, completamento serie e timer recupero
- Riepilogo workout, Progress Score dimostrativo e storico di 8 settimane
- Dashboard PT, filtri clienti, dettaglio performance e AI Coach Insight in preview
- Community privata e condivisa tra PT e allievi, con post e reazioni
- Piani alimentari per cliente con caricamento documento e vista atleta
- Creazione locale di clienti e schede da template
- Persistenza tramite `localStorage` e reset dei dati demo
- Layout responsive per smartphone, tablet e desktop

## Stack

- React 19 e TypeScript
- Vinext / Vite
- Tailwind CSS 4 per la pipeline CSS
- OpenAI Sites plugin per build e hosting Cloudflare-compatible

I grafici sono volutamente leggeri e realizzati in CSS. Il volume segue la formula `serie × ripetizioni × peso`; l'Estimated 1RM è rappresentato come dato demo basato sulla formula di Epley (`peso × (1 + reps / 30)`). Il Progress Score combina progressione, volume, aderenza e consistenza e non è una misura scientificamente validata.

## Avvio locale

Richiede Node.js 22.13 o successivo.

```bash
npm install
npm run dev
```

Aprire `http://localhost:3000`.

## Verifica e build

```bash
npm run lint
npm run build
```

## Deploy

Il progetto viene pubblicato automaticamente su GitHub Pages a ogni push sul branch `main` tramite `.github/workflows/deploy-pages.yml`.

URL previsto: `https://giuseppecredit1111.github.io/demo-gym-management/`

La build statica può essere verificata localmente con `npm run build:pages`. La build standard resta disponibile per OpenAI Sites.

## Struttura

- `app/page.tsx`: dati mock, stato locale e tutti i flussi interattivi
- `app/globals.css`: design system, layout e responsive behavior
- `app/layout.tsx`: metadata e shell HTML
- `.openai/hosting.json`: configurazione hosting Sites

Questa è una validation demo senza backend, autenticazione o pagamenti reali.

## Documentazione

- [PRODUCT.md](PRODUCT.md): visione, utenti, flussi e direzione del prodotto
- [ARCHITECTURE.md](ARCHITECTURE.md): struttura tecnica, stato, build e limiti
- [AGENTS.md](AGENTS.md): regole operative per chi modifica il repository
