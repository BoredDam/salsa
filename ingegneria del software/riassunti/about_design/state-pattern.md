# State
È un design pattern di tipo comportamentale.

## Descrizione del problema
Desidero variare il comportamento di un oggetto, in funzione del suo stato interno.

## Soluzione
Creo un'interfaccia `State` per gli stati. Quest'interfaccia dovrà contenere dei metodi che riflettono le funzionalità dell'oggetto che cambiano (in funzione del suo stato). Da lì implemento i vari stati, e quindi i metodi. All'interno della classe `Context` inserirò un'istanza di una classe che implementa `State`, e scriverò i metodi in modo da delegare la responsabilità allo state, che cambierà in funzione dello stato interno.

Interfaccia `State`
```Java
public interface State {
    State turnOn();
    State turnOff();
    void greeting();
}
```

Implementazione dello stato **acceso**.
```Java
public class OnState implements State {

    public State turnOn() {
        System.out.println("Already on, human!");
        return this;
    }

    public State turnOff() {
        System.out.println("Bye, human!");
        return new OffState();
    }

    public void greeting() {
        System.out.println("Hi human!");
    }

}
```

Implementazione dello stato **spento**.
```Java
public class OffState implements State {

    public State turnOn() {
        System.out.println("Booting up, human!");
        return new OnState();
    }

    public State turnOff() {
        System.out.println("... *already off, silly human* ...");
        return new OffState();
    }

    public void greeting() {
        System.out.println("...");
    }

}
```

Contesto:
```Java
public class Robot {
    State powerState;

    void greeting() {
        powerState = powerState.greeting(); 
    }

    void turnOn() {
        powerState = powerState.turnOn(); 
    }

    void turnOff() {
        powerState = powerState.turnOff(); 
    }
}
```

È facile descrivere il comportamento delle classi, in funzione degli stati, usando dei diagrammi di stato (delle vere e proprie **macchine a stati finiti** :D).

### Nota bene

Il pattern **State** potrebbe apparire molto simile allo **Strategy**. Tuttavia, le varie strategie del secondo pattern sono molto indipendenti tra loro, mentre gli stati si conoscono, ed è spesso possibile passare da uno State ad un altro. Basti pensare alle funzioni `turnOn` e `turnOff` negli stati `OffState` e `OnState`.