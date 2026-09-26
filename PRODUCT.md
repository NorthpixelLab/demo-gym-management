# PTCommand — Product brief

## Visione

PTCommand è un prodotto di gestione e performance intelligence per Personal Trainer, palestre e atleti. Riduce l'attrito nella registrazione degli allenamenti e trasforma presenze, carichi e costanza in indicazioni immediatamente utili per il coach.

La promessa è semplice: l'atleta sa sempre cosa fare; il PT sa subito chi sta progredendo, chi è fermo e chi richiede attenzione.

## Utenti

### Personal Trainer

Gestisce clienti, programmi, calendario, presenze e comunicazioni. Deve poter intervenire rapidamente senza consultare fogli, chat e app separate.

### Atleta

Consulta il proprio calendario e la scheda, sceglie l'ordine degli esercizi, registra le serie e comunica con il PT. L'esperienza è mobile-first e pensata per l'uso durante l'allenamento.

## Flussi principali

### Intro

Un onboarding visuale presenta la promessa commerciale in tre passaggi: appartenenza attraverso la community, intervento prima dell'abbandono e risultati che rendono visibile il valore del PT. Al termine riporta alla landing, lasciando libera la scelta tra modalità PT e atleta. Il reset riapre l'intro.

### Area PT

- **Oggi:** agenda operativa con orari, clienti e stato degli allenamenti.
- **Calendario:** vista settimanale di chi si allena ogni giorno.
- **Community:** spazio privato del team, visibile e moderabile dal PT.
- **Diete:** gestione dei piani alimentari e caricamento per singolo cliente.
- **Statistiche:** panoramica su miglioramento, plateau, calo e aderenza.
- **Clienti:** elenco, stato, calendario personale, storico e conversazione.
- **Programmi di allenamento:** creazione e modifica di schede riutilizzabili.
- **Builder scheda:** ordine drag-and-drop, serie, ripetizioni, recupero, superserie e tri-serie.

### Area atleta

- **Oggi:** prossimo allenamento e avanzamento settimanale.
- **Calendario:** spostamento o segnalazione di un allenamento saltato.
- **Scheda:** giorni ed esercizi assegnati.
- **Allenamento:** scelta flessibile dell'esercizio, registrazione di carico e ripetizioni, suggerimenti tecnici e timer.
- **Superserie:** alternanza guidata tra esercizi collegati con transizione breve.
- **Progressi:** storico e indicatori dimostrativi.
- **Messaggi:** comunicazione bidirezionale con il PT.
- **Community:** post, traguardi e reazioni con gli allievi dello stesso PT.
- **Dieta:** documento attivo, validità, autore e giornata alimentare.

## Principi di prodotto

1. **A colpo d'occhio:** le informazioni importanti devono essere comprensibili in pochi secondi.
2. **Flessibile in palestra:** l'ordine consigliato non impedisce di scegliere un altro attrezzo.
3. **Azione prima del dato:** ogni segnale deve suggerire una decisione o un approfondimento.
4. **Poco attrito:** valori precompilati, controlli grandi e interazioni brevi.
5. **Coach e atleta sincronizzati:** calendario, assenze e messaggi devono raccontare la stessa situazione.

## Stato della demo

La demo usa dati realistici ma simulati e persiste le modifiche nel `localStorage` del browser. Non include backend, account reali, notifiche push, pagamenti o sincronizzazione tra dispositivi.

Il Progress Score e gli insight sono elementi dimostrativi e non costituiscono misure scientificamente validate o indicazioni mediche.

## Direzione futura

- Backend multi-tenant con ruoli PT, palestra e atleta.
- Autenticazione e inviti cliente.
- Programmi diversi per ogni giorno e libreria esercizi completa.
- Calendario sincronizzato e notifiche reali.
- Messaggistica per singolo cliente con allegati e azioni sul calendario.
- Storico reale di serie, volume, carichi, RPE e record personali.
- Insight spiegabili con regole configurabili dal coach.
- Accessibilità, internazionalizzazione e test su dispositivi reali.
