# Singleton

È un design pattern di tipo creazionale.

## Descrizione del problema
Desidero limitare una classe ad una sola istanza, e fornire un punto di accesso globale alla stessa.

## Soluzione
Il Singleton design pattern, tra i pattern più semplici da implementare, permette di ottenere tutti i requisiti che ci siamo posti.


## Entità coinvolte nel pattern
### Singleton (Classe)
Possiamo rendere una qualsiasi classe del nostro sistema un Singleton, integrando le seguenti modifiche e funzioni.

```java
class Singleton {

    private static Singleton instance;

    private Singleton() {
        /*constructor*/
    };

    public static Singleton getIstance() {
        if(instance == null){
            instance =  new Singleton();
        }
        return istance;
    };

    /*...*/

}
```


## Altro degno di nota da sapere
Facilmente utilizzabile in combinazione con il design pattern NullObject, per creare singole istanze di comportamenti di default (come i NullNode nelle implementazioni degli alberi BST).
## About Java
