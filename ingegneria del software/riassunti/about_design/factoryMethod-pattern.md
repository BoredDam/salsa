# Factory Method

È un design pattern di tipo creazionale.

## Descrizione del problema
Desidero incapsulare la logica di creazione di un oggetto, all'interno di una classe dedicata. Voglio poter stabilire a run-time quale classe (o implementazione) istanziare.

## Soluzione
Delego la creazione di un oggetto ad un metodo, contenuto in una classe vera e propria.


## Entità coinvolte nel pattern
### Factory (Interfaccia)
È l'interfaccia della nostra factory.
```java
interface Factory {
    Product factoryMethod();
    /*other functions*/
}
```
### ConcreteFactory (Classe)
È un'implementazione dell'interfaccia Factory.

```java
class ConcreteFactory implements Factory {
    Product factoryMethod() {
        return new ConcreteProduct();
    };
    /*other functions*/
}
```

### Product (Interfaccia)

```java
interface Product {
    void foo();
    /*functions of
    products interface*/
}
```


### ConcreteProduct (Classe)

```java
class ConcreteProduct implements Product {
    void foo(){
        /*foo behaviour*/
    };

    /*functions of the
    "products" interface*/

    /*functions of the
    "ConcreteProduct" class*/
}
```

## Altro degno di nota da sapere

### `static` factory method
Rendendo static il creator, il factory method diventa un **metodo di classe** globale. È più rigido, non può essere overrideato, ma non richiede né interfaccia AbstractCreator, né istansiazione del ConcreteCreator

### Factory method parametrico
Inserendo dei parametri al factory method, si può supportare la creazione di più oggetti all'interno dello stesso creator.
```java
public class StCreator {
    private static boolean a = true;
    public static IStudente getStudente() {
        if (a) {
            return new Studente();
        }

        return new Sospeso(0);
    }
}
```
###


### Object Pool
È un pool di istanze già create. Il factory method può fornire al client un'istanza di una classe già creata. Il pool è un singleton. Si crea quindi un **Multiton**. I client devono restituire l'oggetto alla fine dell'utilizzo.

```java
import java.util.LinkedList;
/*creator pool is a factory method
with an object pool*/

public class CirclePool extends ShapeCreator {
    private LinkedList<Shape> pool = new LinkedList<Shape>();

    /*getShape() returns an object
    from the object pool*/
    public Shape getShape() {
        Shape s;
        if (pool.size() > 0) {
            s = pool.removeFirst();
        } else {
            s = new Circle(); /*concrete product*/
        }
        return s;
    }

    /*releaseShape() puts an object
    back in the object pool*/
    public void releaseShape(Shape s) {
        pool.addLast(s);
    }
}
```
### Dependency Injection
Un factory method potrebbe effettuare ciò che in gergo è chiamata **dependency injection**. Consiste nella delega della creazione di dipendenze tra due o più oggetti ad un oggetto esterno. Le dipendenze sono quindi create a run-time, in maniera dinamica. Le classi non saranno quindi dipendenti tra loro.

### Creator con riflessione
La **Reflection** API fornisce un modo per passare ad un metodo una classe come parametro formale.
```java
import java.lang.reflect.InvocationTargetException;

import Products.Menu;

public class MenuFactory {

    /*type of the Menu class object
    I want to create.*/
    private Class<? extends Menu> m;
    public MenuFactory(Class<? extends Menu> m){ 
        this.m = m;
    }
    
    /*Menu constructor. it gets the 
    constructor from the "m" class.*/
    public Menu getMenu() {
        try {
            return m.getConstructor().newInstance();
        } catch (InstantiationException | ... | e) {
            e.printStackTrace();
            return null;
        }
    }
}
```

## About Java
