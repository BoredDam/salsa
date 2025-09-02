# NullObject

Non è un design pattern della GoF.

## Descrizione del problema
Devo definire un comportamento di default (o in particolare, vuoto) per delle classi. 

## Soluzione
La nostra classe ha un'interfaccia.
Incapsulando il comportamento "vuoto" all'interno ad un'altra implementazione dell'interfaccia, e quindi, creando un **NullObject**, è possibile definire ad hoc i metodi.

## Entità coinvolte nel pattern
### AbstractObject (Interface)
È ciò con cui il client si interfaccia per interagire con gli oggetti.

```java
interface AbstractObject {
    void foo();
}
```

### NullObject (Class)
Implementazione null della classe.

```java
class NullObject implements AbstractObject {
    void foo() {
        /*"do nothing" behaviour
        or default behaviour
        whtvr fits the job*/
    };
}
```

### ConcreteObject (Interface)
Una o più classi concrete che implementano l'interfaccia.
```java
class ConcreteObject implements AbstractObject {
    void foo() {
        /*regular behaviour of foo()
        for the ConcreteObject class*/
    };
}
```

## Altro degno di nota da sapere

## About Java
