# Template Method

È un design pattern di tipo comportamentale.

## Descrizione del problema
Desidero tenere lo scheletro di un algoritmo uguale, ma modificarne specifici passi nelle sottoclassi (o implementazioni).

## Soluzione
L'algoritmo (con la sua struttura generale) sarà definito all'interno di una classe astratta (o interfaccia). Nello specifico, il metodo che lo conterrà, sarà proprio il Template Method. È ideale definirlo come `final`. Inoltre, bisognerà definire dei metodi astratti (chiamati magari `part()` o `step()`). Dichiarandoli astratti, tutte le sottoclassi o implementazioni dell'interfaccia, saranno costrette a definire un comportamento per i vari passi dell'algoritmo.


```Java
public interface AbstractAlgorithm {
    void operationA();
    void operationB();

    public final void TemplateMethod() {
        partA();
        partB();
    }
}
```

```Java
public class Alg1 implements AbstractAlgorithm {
    void partA() {
        System.out.println("Alg1 - PartA");
    }
    void partB() {
        System.out.println("Alg1 - PartB");
    }
}
```
```Java
public class Alg2 implements AbstractAlgorithm {
    void partA() {
        System.out.println("Alg2 - PartA");
    }
    void partB() {
        System.out.println("Alg2 - PartB");
    }
}
```

Per quanto possa ricordare lo strategy pattern, sono molto differenti.


**Strategy** è basato sulla **composizione**, **Template Method** è basato sull'**ereditarietà**. Inoltre, mentre **Template Method** è statico e opera al livello di classe, **Strategy** permette scelte a run-time, lavorando sull'oggetto.