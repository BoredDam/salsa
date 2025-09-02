# Testing

Questi appunti sono incompleti, ma potrebbero fornire dei chiarimenti rispetto alle nozioni trattate.

## Complessità

### Complessità accidentale
Indica complessità causata da **scelte effettuate in fase di programmazione**. Può essere risolta cambiando il codice o il linguaggio usato.

### Complessità intrinseca
Rimane a prescindere dalla complessità accidentale, e può essere controllata sviluppando comportamenti a run-time più prevedibili.

La complessità intrinseca è causata quindi dal non conoscere tutti i possibili esiti di una determinata sezione di codice.

Sono dette **fault** le sezioni di codice che creano errore (possono essere errori in fase di compilazione, a run-time, o banalmente errori logici). Le conseguenze di un fault, sono dette **failure**, bug, difetti o anomalie.

## Prove di correttezza

### Validazione

Consiste nel testing del software. La validazione viene effettuata fornendo vari input al codice, e verificando la correttezza dell'output.

I test possono essere di due tipi:
- Black-box: i test sono basati esclusivamente sull'input e l'output atteso
- White-box: i test sono basati sulla conoscenza del codice. L'obiettivo è verificare tutti i casi limite.

### Verifica
Consiste in un analisi formale. ogni meccanismo interno viene verificato nella correttezza. Si guardano non solo i risultati, ma le implementazioni.

Data la cura con cui deve essere effettuata la verifica, e la crescente complessità del software, questa può essere eseguita solo su porzioni minori di questi ultimi.

Alcuni strumenti permettono di analizzare i software tramite utilizzo di linguaggi formali. Permettono ad esempio di verificare la terminazione di un ciclo.

## Testing

### Fasi del testing

1. Scelta del (-la sezione di) software da testare

2. Impostazione dell'ambiente di testing

3. Selezione di un set di input basato su vari criteri

4. Valutazione degli output ottenuti

Se il codice è stato scritto seguendo bene il criterio di singola responasbilità, è possibile creare test che validano le funzionalità di un'intera classe.

## Terminologie

**Test unitario**: indica un test eseguito su una funzione o una singola classe

**Regression testing**: test già eseguiti in precedenza, usati per verificare la correttezza dopo aver effettuato cambiamenti al codice.

**Test suite**: insieme di test di input.

**System Verification Group**: team cui scopo è quello di effettuare il testing.

## Livelli di test
- **Test unitari**: testano funzionalità funzionalità atomiche

- **Test d'integrazione**: testano funzionalità complesse risultato di più funzionalità atomiche.

- **Test funzionali**: testano le funzionalità previste dalle specifiche del sistema, mettendo a confronto col design.

- **Test di sistema**: si testa l'intero sistema, anche negli aspetti tecnici.

- **Test di accettazione**: si verifica il sistema in vari scenari d'utilizzo reale.

