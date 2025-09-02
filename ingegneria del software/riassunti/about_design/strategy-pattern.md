# Strategy
È un design pattern di tipo comportamentale.

## Descrizione del problema
Desidero poter scegliere un algoritmo a run-time per stabilire più strategie.

## Soluzione
Creo un'interfaccia comune a tutte le strategie, e la faccio implementare a tutte le varianti di strategie che desidero. Ogni versione dell'algoritmo viene inserita in una classe differente. Incapsulerò un'istanza di questa classe all'interno del contesto che la necessità. Ottengo la possibilità di cambiare l'oggetto che implementa l'interfaccia `Strategy` a run-time, in quanto sfrutta la composizione.


```Java
public interface Printer {
    void print();
}
```

```Java
public class NamePrinter implements Printer {
    void print() {
        System.out.println("gonna print my name... SIKE");
    };
}
```

```Java
public class SurnamePrinter implements Printer {
    void print() {
        System.out.println("gonna print my surname... HELL NAH");
    };
}
```

```Java
public class Context {
    Printer printer;

    public static void main(String[] args) {
        printer = new NamePrinter();
        printer.print(); // "gonna print my name... SIKE"
        printer = new SurnamePrinter();
        printer.print(); // "gonna print my surname... HELL NAH"
    }
    
}
```

Per quanto possa ricordare il Template Method pattern, sono molto differenti.

**Strategy** è basato sulla **composizione**, **Template Method** è basato sull'**ereditarietà**. Inoltre, mentre **Template Method** è statico e opera al livello di classe, **Strategy** permette scelte a run-time, lavorando sull'oggetto.