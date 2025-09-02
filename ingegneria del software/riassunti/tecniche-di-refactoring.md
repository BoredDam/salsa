# Refactoring

Il refactoring è un procedimento cui obiettivo è **migliorare un sistema software senza modificarne le funzionalità**. 
Rispettare gli stessi requisiti funzionali, modificando il codice.

Che codice vogliamo ottenere?
- Codice **riutilizzabile**
- Codice **leggibile**
- Codice **mantenibile**
- Codice **scalabile**
- Codice **minimale**
- **Meno debito tecnico** nella progettazione.

Il **refactoring** va effettuato **durante lo sviluppo**: 
in questo modo, è possibile iniziare a stendere codice, seppur questo non sarà definitivo: diventa più semplice adeguare il codice a nuovi requisiti o cambiamenti, permettendo di evolvere la progettazione in piccoli passi.

Inoltre, modificare il software senza cambiarne le funzionalità, obbliga a una **comprensione approfondita del codice**, permettendo più facilmente di individuare eventuali **bug**. 

```Java
void printOwing() {
    printBanner();

    System.out.println("name: " + name);
    System.out.println("amount: " + getOutstanding());
}
```
Diventerà...

```Java
void printOwing() {
    printBanner();
    printDetails(getOutstanding());
}

void printDetails(double outstanding) {
    System.out.println("name: " + name);
    System.out.println("amount: " + outstanding);
}
```
### Approccio generale al Refactoring

- Usare **tecniche di refactoring note**.
- Fare refactoring **SEMPRE**.
- Osservare se i risultati dei test sono stati modificati dal refactoring.



## Tecnica di refactoring - Estrai metodo
Un frammento di codice può essere estratto, inserito in un metodo cui nome esplicita la funzionalità, e sostituito da quest'ultimo.

- **Meno commenti** necessari.
- Codice **riutilizzabile**.
- Il codice che usa i metodi estratti, diventa di più alto livello.
- Facilita l'**overriding** nelle sottoclassi.

## Tecnica di refactoring - Rimpiazza temporanee con query

All'interno del codice, vengono spesso usate **variabili temporanee** per contenere il risultato di alcune **espressioni**.

Sostituire queste variabili temporanee con un metodo di tipo **query** facilita la leggibilità del codice.

Permette inoltre di riutilizzare variabili che sarebbero altrimenti definite solo localmente.

```Java
double calculateTotal() {
    double basePrice = quantity * itemPrice;
    if (basePrice > 1000) {
        return basePrice * 0.95;
    } else {
        return basePrice * 0.98;
    }
}
```

diventerà...

```Java
double calculateTotal() {
    if (basePrice() > 1000) {
        return basePrice() * 0.95;
    } else {
        return basePrice() * 0.98;
    }
}


double basePrice() {
  return quantity * itemPrice;
}
```

Attenzione! Questo metodo può essere utilizzato solo su variabili temporanee che vengono assegnate una sola volta! Usare la keyword `final` alla prima dichiarazione della variabile e compilare, permetterà di verificare molto velocemente se questa è stata riassegnata.

In tal caso, utilizzare prima la prossima tecnica di refactoring: la **split temp var**, ossia...

## Dividi le variabili temporanee

Le variabili temporanee possono essere utili in molteplici circostanze. Tuttavia, la loro riassegnazione in contesti differenti rompe il principio di **singola responsabilità**. 

```Java
void printMeasures() {

    double temp = 2 * (height + width); // temp contiene il perimetro
    System.out.println(temp);

    temp = height * width; // riassegnazione, temp contiene l'area
    System.out.println(temp);
}
```

```Java
void printMeasures() {

    final double perimeter = 2 * (height + width);
    System.out.println(perimeter);

    final double area = height * width;
    System.out.println(area);
}
```

Avremo un codice su cui sarà addirittura possibile applicare la precedente tecnica di refactoring!

```Java
void printMeasures() {
    
    System.out.println(perimeter());
    System.out.println(area());
}


double perimeter() {
    return 2 * (height + width);
} 

double area() {
    return height * width;
} 
```

### Unica eccezione valida per variabili temporanee riassegnate ben nota

Variabili dei cicli iterativi! Quelle hanno senso. Hanno ogni volta la stessa responsabilità.