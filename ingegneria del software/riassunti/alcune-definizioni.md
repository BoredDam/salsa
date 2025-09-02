# Alcune definizioni

## OOP

### Proprietà principali
Incapsulamento, ereditarietà, polimorfismo.
Risolve le problematiche della programmazione strutturata, offre nuovi livelli di astrazione (grazie appunto agli ADT) e offre anche un nuovo modo per gestire le risorse.

### ADT - Abstract Data Type
È un concetto teorico. Definisce un tipo di dato attraverso il comportamento da esso previsto.
L'ADT di uno stack prevede pop() e push(), ma non si offrono dettagli relativi alle implementazioni.

Gli ADT sono realizzati in Java tramite classi astratte (o soltanto metodi), o meglio ancora, interfacce, che seguono alla lettera i principi degli ADT.

### Eccezioni
La OOP si incastra alla perfezione con le Exceptions, che permettono di gestire gli errori in esecuzione. In Java, le Exceptions sono oggetti, che disaccoppiano la gestione degli errori dal loro rilevamento.

### Parametrizzazione
Il binding dinamico offre la possibilità, a run-time, di risolvere il tipo di una variabile parametrica.

In questo modo diventa possibile stabilire a tempo di esecuzione il tipo di una determinata variabile, generalizzando quanto possibile il software.

È un'altra sfaccettatura del polimorfismo.

## UML

### Modellazione

La creazione di un'astrazione della realtà.

### Modello
È una descrizione astratta di un sottoinsieme di un sistema.

### Vista
Si intende un sottoinsieme di aspetti del modello.
- Logical view
- Component view
- Process view
- Deployment view

### Notazione
Insieme di regole grafiche o testuali per rappresentare viste.

### Diagrammi UML
Unified Modeling Language. Definiscono un insieme di regole per la rappresentazione di sistemi (principalmente Object Oriented).

### Lista diagrammi UML

#### Use Case

Descrive le funzionalità offerte da un sistema, esplicitando anche attori esterni, confini del sistema. Utile per stabilire i requisiti di sistema e chi interagisce.

#### Class

Esplicita le classi del sistema (anche classi astratte e interfacce), definendone le relazioni (quali implementazione, ereditarietà, composizione, dipendenze d'uso), gli attributi e i metodi. Sono i diagrammi UML più popolari.

#### Activity
Descrive una sequenza di attività relative ad un algoritmo. È possibile specificare anche conditionals che biforcano il flusso di attività.


#### Collaboration
Descrive le interazioni tra gli oggetti di un sistema. Il flusso è esplicitato da frecce, che indicano quale metodo o messaggio viene inviato da quale entità, a quale entità.

#### Sequenza


#### State
Descrivono gli stati interni relativi alle entità del sistema, esplicitando anche cause e conseguenze dei cambi di stato. Può essere indicato uno stato iniziale, e uno o più stati finali. Sono dei veri e propri automi a stati finiti.
