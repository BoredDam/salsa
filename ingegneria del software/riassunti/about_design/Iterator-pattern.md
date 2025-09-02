# Iterator

È un design pattern di tipo comportamentale.

## Descrizione del problema
Attraversare elementi di un aggregato senza esporre al client la sua struttura.

## Soluzione
Il design pattern Iterator offre un'interfaccia uniforme. In questo modo, il codice client non deve cambiare in funzione dell'aggregato usato, aumentando la riusabilità del codice.

Il client non deve conoscere la struttura dell'aggregato. A quello, ci penserà il ConcreteIterator, a cui il client si potrà interfacciare tramite l'interfaccia Iterator.


## Entità coinvolte nel pattern

### Aggregato (Interfaccia)
È l'interfaccia della nostra struttura dati. Deve contenere un factory method per creare l'iteratore.
```java
interface Aggregate {
    //...
    //..
    Iterator createIterator();
}
```
### AggregatoConcreto (Classe)
È un'implementazione dell'interfaccia Aggregate.

```java
class ConcreteAggregate implements Aggregate {
    //...
    //..
    Iterator createIterator() {
        /* factory method code here
        has to return an iterator object*/
    };
}
```

### Iteratore (Interfaccia)

```java
interface Iterator {
    Object next();
    boolean hasNext();
}
```


### IteratoreConcreto (Classe)

```java
Class ConcreteIterator implements Iterator {
    Object next() {
        /*return next item in the aggregate
        and, if it exists, move the iterator to the next item*/
    };

    boolean hasNext() {
        /*return True if the aggregate has more items to visit*/
    };
}
```

## Altro degno di nota da sapere

### Più iteratori, più attraversamenti
È possibile avere più iteratori, e quindi gestire più attraversamenti in contemporanea, sul nostro aggregato. Gli attraversamenti possono seguire politiche differenti.

### Strutture dati diverse, implementazioni diverse

Se l'interfaccia **Iterator** rimane uguale, le implementazioni devono conoscere la struttura dati, ed avere un'implementazione ad hoc, più o meno intuitiva. La complessità dell'implementazione dell'iteratore è strettamente legati alla tipologia di struttura dati usata dakk'aggregato.


## About Java


### Java Collection Framework
La Java Collection Framework fornisce un insieme di strutture dati (chiaramente con Interfacce e opportune classi concrete che le implementano) per offrire al programmatore delle soluzioni semplici, efficaci e ottimizzate

In funzione di questi aggregati, fornisce anche tante opzioni per attraversare le proprie Collection. Tra questi, abbiamo

#### Modi per attraversare le Collections in Java
- Interfaccia iterable e Enhanced for-loop.
- Interfaccia iterable e metodo `Collection.forEach()`.
- Usando esplicitamente l'oggetto Iterator.
- Sulle liste, oggetto ListIterator.
- Enumeration, deprecata.
- Ciclo for, senza iteratore.
- Interfaccia stream, usando `Collection.stream().forEach()`.