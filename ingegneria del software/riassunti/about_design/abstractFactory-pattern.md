# Abstract Factory
È un design pattern di tipo creazionale.

## Descrizione del problema
Voglio facilitare la creazione di famiglie di oggetti simili.

## Soluzione
L'abstract factory fornisce un'interfaccia per la creazione di famiglie di oggetti correlati.

## Entità coinvolte nel pattern
### AbstractFactory (Interface)


```java
interface AbstractFactory {
    This createThis();
    That createThat();
}
```
### ConcreteFactories (Classes)
```java
class ConcreteFactoryA implements AbstractFactory {
    Product createThis() {
        return new ThisProductA;
    }
    Product createThat() {
        return new ThatProductA;
    }
}

class ConcreteFactoryB implements AbstractFactory {
    Product createThis() {
        return new ThisProductB;
    }
    Product createThat() {
        return new ThatProductB;
    }
}
```


## Altro degno di nota da sapere

## About Java
