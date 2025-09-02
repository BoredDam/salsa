# Principi di Design 

## Principio di singola responsabilità

>Metodi e classi devono avere una sola responsabilità.

 **Un metodo** deve svolgere **un singolo compito**. **Una classe** deve rappresentare **un singolo concetto**.

## Programmare a interfacce, non a implementazioni

> Bisogna programmare riferendosi ad interfacce, non ad implementazioni.

Usare classi astratte e interfacce,  definendo interfacce comuni per insiemi di classi. In questo modo, i programmi non sono vincolati alle implementazioni delle classi, ma alle sole interfacce.

In questo modo, si stabiliscono dei comportamenti concepiti per le classi che usano una data interfaccia, senza definirne i dettagli implementativi 

Le Java Collections offrono numerose interfacce (List, Set, Queue) che possono essere usate per interagire con varie implementazioni. List può essere implementata da ArrayList, LinkedList, Vector, etc.

Diventa possibile modificare l'implementazione senza dover modificare la struttura generale del programma, ma solo specificando un'implementazione diversa.

## Composition over Inheritance

> Preferire la composizione all'ereditarietà.


- Creando **meno dipendenze implementative** (*loose coupling*, accoppiamento lasco).

- Isolando i comportamenti delle classi, **seguendo il principio di singola responsabilità**. 

- Godendo di comportamenti che possono cambiare a run-time.


In generale, diremo che l'ereditarietà crea una relazione di tipo "is-a".  Una composizione crea una relazione di tipo "has-a".

## Usare i tipi parametrici

Forniscono la versatilità del binding dinamico a run-time. Permettono di comporre nuovi sistemi in qualsiasi sistema Object Oriented.



# Design Pattern

## Introduzione

> I design pattern descrivono degli **schemi generali di risoluzione di problematiche comuni** che si possono presentare nei nostri sistemi software orientati a oggetti.

Ogni pattern presenta:

- Nome del pattern.
- Descrizione del problema.
- Soluzione (con opportuni schemi).
- Conseguenze sul nostro sistema e trade-off vari.

Esistono tre tipologie principali di pattern:

- **Creazionali**: gestiscono e regolano la creazione (e i meccanismi di creazione) di oggetti.

- **Strutturali**: gestiscono la composizione di oggetti.

- **Comportamentali**: gestiscono la comunicazione tra più oggetti e il lloro comportamento generale, anche in termini di algoritmi.
