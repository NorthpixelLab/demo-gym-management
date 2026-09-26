# Architettura

## Panoramica

PTCommand è attualmente una single-page demo in React e TypeScript. La UI, i dati mock e la maggior parte della logica applicativa risiedono in `app/page.tsx`; lo stile globale e responsive risiede in `app/globals.css`.

```text
Browser
  ├─ React UI
  ├─ stato in memoria
  └─ localStorage
       ├─ clienti
       ├─ programmi
       ├─ calendario atleta
       ├─ messaggi demo
       ├─ community privata
       └─ piani alimentari
```

Non esistono API, database o autenticazione. Ogni dispositivo e browser mantiene una copia locale indipendente dei dati.

## Stack

- React 19 e TypeScript
- Vinext per sviluppo e build principale
- Vite per la build statica GitHub Pages
- Tailwind CSS 4 nella pipeline CSS
- ESLint per i controlli statici
- GitHub Actions e GitHub Pages per il deploy pubblico
- OpenAI Sites come destinazione di hosting alternativa

## Entry point e file principali

- `app/page.tsx`: modello dati, stato, navigazione e componenti della demo.
- `app/globals.css`: token, componenti visivi e breakpoint responsive.
- `app/layout.tsx`: struttura HTML e metadata.
- `src/main.tsx`: entry point della build statica Vite.
- `vite.pages.config.ts`: base path e output per GitHub Pages.
- `vite.config.ts`: configurazione Vinext/OpenAI Sites.
- `.github/workflows/deploy-pages.yml`: pipeline GitHub Pages.
- `.openai/hosting.json`: configurazione logica OpenAI Sites.

## Modello dati

I tipi principali sono definiti in `app/page.tsx`:

- `Client`: profilo, stato, score, andamento, presenze e programma.
- `Program`: nome, frequenza, clienti ed esercizi.
- `Exercise`: nome, icona, serie, ripetizioni, carico, recupero e gruppo.
- `Message`: mittente, testo e ora.
- `ScheduleState`: `planned`, `completed` o `skipped`.

Il campo `Exercise.group` collega esercizi appartenenti alla stessa superserie o tri-serie. Durante l'allenamento, gli esercizi con lo stesso gruppo vengono alternati con una transizione breve.

## Gestione dello stato

La navigazione è gestita con una union `View` e rendering condizionale, senza router. Lo stato globale vive nel componente `App` e viene passato ai componenti tramite props.

Le chiavi locali usate dalla demo sono:

- `progressi-clients`
- `progressi-programs`
- `progressi-days`
- `progressi-schedule`
- `progressi-messages`
- `progressi-community`
- `progressi-diets`

Il reset cancella il `localStorage` e ripristina i dati iniziali.

## Build e deploy

### Sviluppo

```bash
npm run dev
```

### Controlli

```bash
npm run lint
npm run build:pages
```

### GitHub Pages

La build Vite usa `/demo-gym-management/` come base path e produce `pages-dist`. Un push su `main` attiva la pubblicazione automatica.

### OpenAI Sites

La build standard usa Vinext e genera un output compatibile con l'ambiente di hosting configurato nel repository.

## Limiti attuali

- Dati e conversazioni non sono condivisi tra browser o dispositivi.
- I messaggi demo non sono ancora separati per cliente.
- I programmi mostrano un set di esercizi semplificato.
- Non esistono autorizzazioni o protezione dei dati.
- Grafici e insight sono rappresentazioni dimostrative.
- La struttura monolitica è adatta alla validazione, non a un prodotto in scala.

## Evoluzione consigliata

Prima di introdurre un backend, separare progressivamente:

1. `app/page.tsx` in feature dedicate (`coach`, `athlete`, `workouts`, `messages`).
2. Dati mock e tipi in moduli indipendenti.
3. Stato e persistenza dietro repository/service interfaces.
4. Componenti condivisi in un piccolo design system.
5. Navigazione condizionale in route reali.

Con un backend, mantenere separati dominio, accesso ai dati e UI; introdurre identificativi stabili, isolamento tenant, autorizzazioni per ruolo, audit delle modifiche e gestione coerente dei fusi orari.
