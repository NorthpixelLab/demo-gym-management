# AGENTS.md

## Obiettivo del repository

Questo repository contiene la demo interattiva di **PTCommand**, un prodotto per Personal Trainer e atleti. Ogni modifica deve preservare la qualità della demo commerciale, la coerenza tra area PT e area atleta e la possibilità di pubblicare su GitHub Pages.

Prima di modificare il prodotto, leggere:

- `README.md` per setup e deploy.
- `PRODUCT.md` per utenti, flussi e principi.
- `ARCHITECTURE.md` per struttura, stato e limiti tecnici.

## Regole di implementazione

- Usare React e TypeScript senza introdurre nuove dipendenze salvo necessità concreta.
- Conservare il funzionamento sia della build Vinext sia della build statica Vite.
- Non modificare il base path `/demo-gym-management/` senza aggiornare anche il deploy.
- Preservare i dati già presenti nel `localStorage`; le nuove proprietà devono avere fallback sicuri.
- Mantenere i flussi PT e atleta coerenti: una modifica a calendario, scheda o messaggi deve essere riflessa dove pertinente in entrambe le viste.
- Usare dati realistici ma chiaramente dimostrativi; non presentare score o insight come valutazioni scientifiche o mediche.
- Evitare interazioni senza effetto. Pulsanti, tab e card cliccabili devono produrre un risultato visibile.
- Mantenere l'interfaccia responsive e mobile-first per l'area atleta.
- Riutilizzare stile, spaziature, colori e componenti esistenti prima di introdurre nuove varianti.
- Non aggiungere segreti, token, credenziali o dati personali reali al repository.

## Indicazioni UX

- Testi in italiano, brevi e naturali.
- Mostrare prima l'informazione operativa, poi il dettaglio.
- Rendere evidenti stati come completato, previsto, saltato e in ritardo.
- Non bloccare l'atleta su un ordine rigido degli esercizi.
- Per superserie e tri-serie, guidare esplicitamente il passaggio al prossimo esercizio e usare recuperi coerenti.
- Ogni nuova funzione deve risultare comprensibile senza tutorial esterno.

## File e responsabilità

- `app/page.tsx`: flussi, dati mock e interazioni.
- `app/globals.css`: design system e responsive.
- `app/layout.tsx`: metadata.
- `vite.pages.config.ts`: build GitHub Pages.
- `.github/workflows/deploy-pages.yml`: pubblicazione automatica.

La struttura è volutamente compatta. Per interventi piccoli, evitare refactor estesi non richiesti. Se la complessità cresce, estrarre componenti per feature mantenendo invariato il comportamento.

## Verifica obbligatoria

Prima di concludere una modifica eseguire:

```bash
npm run lint
npm run build:pages
git diff --check
```

Correggere errori reali prima del commit. Gli avvisi noti di Lightning CSS relativi alle direttive Tailwind non bloccano attualmente la build, ma non devono nascondere nuovi errori.

## Git e pubblicazione

- Lavorare sul branch previsto dal task e non sovrascrivere modifiche non correlate.
- Usare commit brevi e descrittivi.
- Il push su `main` pubblica automaticamente GitHub Pages.
- Non usare comandi distruttivi come `git reset --hard`.
- Non riscrivere la cronologia salvo richiesta esplicita.

## Definition of done

Una modifica è completa quando:

1. soddisfa il flusso richiesto;
2. non rompe le viste PT e atleta;
3. funziona su layout desktop e mobile;
4. preserva reset e persistenza locale;
5. supera lint, build statica e controllo whitespace;
6. aggiorna la documentazione se cambia prodotto, architettura o procedura.
