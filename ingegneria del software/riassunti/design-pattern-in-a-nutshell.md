# Design pattern in a nutshell

## Principi di design

### Principio di singola responsabilità

>Metodi e classi devono avere una sola responsabilità.

 **Un metodo** deve svolgere **un singolo compito**. **Una classe** deve rappresentare **un singolo concetto**.

### Programmare a interfacce, non a implementazioni

> Bisogna programmare riferendosi ad interfacce, non ad implementazioni.

Usare classi astratte e interfacce,  definendo interfacce comuni per insiemi di classi. In questo modo, i programmi non sono vincolati alle implementazioni delle classi, ma alle sole interfacce.

In questo modo, si stabiliscono dei comportamenti concepiti per le classi che usano una data interfaccia, senza definirne i dettagli implementativi 

Le Java Collections offrono numerose interfacce (List, Set, Queue) che possono essere usate per interagire con varie implementazioni. List può essere implementata da ArrayList, LinkedList, Vector, etc.

Diventa possibile modificare l'implementazione senza dover modificare la struttura generale del programma, ma solo specificando un'implementazione diversa.

### Composition over Inheritance

> Preferire la composizione all'ereditarietà.


- Creando **meno dipendenze implementative** (*loose coupling*, accoppiamento lasco).

- Isolando i comportamenti delle classi, **seguendo il principio di singola responsabilità**. 

- Godendo di comportamenti che possono cambiare a run-time.


In generale, diremo che l'ereditarietà crea una relazione di tipo "is-a".  Una composizione crea una relazione di tipo "has-a".

### Usare i tipi parametrici

Forniscono la versatilità del binding dinamico a run-time. Permettono di comporre nuovi sistemi in qualsiasi sistema Object Oriented.

## Introduzione ai Design pattern

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


## Lista dei pattern

### Creazionali
- Singleton ☑ - Una classe, una sola istanza. Punto d'accesso globale.

- Factory methd ☑ - Delega la creazione di un oggetto a un metodo. La scelta dell'oggetto avviene nelle sottoclassi.

- Abstract Factory ☑ - Un'interfaccia che raccoglie logiche di creazione per più oggetti appartenenti ad un insieme. Le sottoclassi ne definiscono lo "stile" o la "famiglia".

- Builder ☑ - Si mette in mezzo tra il client e il costruttore di una determinata classe, per semplificare la creazione. Permette inoltre un manager che raccoglie dei preset di oggetti.

- Prototype ☑ - Metodo `clone()` per creare copie di oggetti.

### Strutturali
- Adapter ☑ - Implementa un'interfaccia e incapsula al suo interno un oggetto legacy che non la implementa. Permette di adattare una classe già definita a un'interfaccia tramite un adattatore.

- Bridge ☑ - Permette di disaccoppiare una gerarchia di astrazioni da una gerarchia di corrispondenti implementazioni. Utile per evitare di dover definire troppe varianti.

- Composite ☑ - Struttura di composizione ad albero. Gli oggetti sono foglie, gli altri nodi sono composite.

- Decorator ☑ - Aggiungere funzionalità dinamicamente ad un oggetto tramite composizione in un wrapper. Ogni decorator + il base object eseguirà i comandi.

- Facade ☑ - Compone vari oggetti con cui il client dovrebbe interagire, in una classe facciata semplice e intuitiva.

- Flyweight ☑ - Moltissime istanze di oggetti possono riempire la RAM. Se questi oggetti hanno tante cose in comune (assets, attributi o stati interni) è possibile creare un'istanza contenuta in tutti gli oggetti numerosi, contenente i dati comuni, per risparmiare in termini di spazio.

- Proxy ☑ - Si fa da intermediario tra il client e un servizio, incapsulandolo. Può effettuare preprocessing o postprocessing di una richiesta: filtrare richieste, inserire in cache risposte. Implementa la stessa interfaccia dello stesso servizio. In questo modo, il client può interagire col proxy come interagirebbe col servizio. Il proxy si frappone tra il client e un oggetto.




### Comportamentali
- Iterator ☑ - Permette di navigare tra gli elementi di un aggregato, senza esporne la struttura. Supporta vari tipi di scorrimento.

- Command ☑ - Trasforma una richiesta in un oggetto a se stante. Prende nel costruttore un oggetto, ed esegue una serie di istruzioni di quest'ultimo.

- Observer ☑ - Permette di creare un servizio di iscrizione, relativo ad aggiornamenti di un oggetto, per altri oggetti. L'oggetto osservato è detto publisher, ed eseguendo una `notify(state)`, eseguirà una `subscriber.update(state)` su tutti i subscriber, aggiornandoli di un cambiamento di stato, e facendoli reagire a ciò.

- Chain of Responsibility ☑ - Crea una struttura ad albero di Handler, tramite composizione. Solo uno tra gli handler soddisfa la richiesta, non tutti come nei decorator.

- Template Method ☑ - Classe astratta contenente un algoritmo suddiviso in più metodi astratti. Questi metodi astratti devono essere sovrascritti mandatoriamente dalle sottoclassi, creando più implementazioni dello stesso algoritmo, per ogni sottoclasse.

- Strategy ☑ - Simile al template method, ma basata sulla composizione. L'oggetto contenuto dal contesto, è detto "strategia". Il contesto avrà dei metodi che affideranno la richiesta (o del tutto, o in parte) alla strategia, come nel caso del sortBy. La strategia è scelta a run-time, e può cambiare.

- State ☑ - Se il mio oggetto ha degli stati da cui dipende il comportamento di alcuni metodi, passo la richiesta ad un oggetto di tipo state. Questo può inoltre transizionare da uno stato all'altro. L'override dei metodi definiti nell'interfaccia `State` permette di determinare a run-time quale metodo eseguire.

- Visitor ☑ - Suddivide gli algoritmi dalle strutture su cui operano. L'oggetto su cui opera l'algoritmo, accetta quest'ultimo (visitor) ed esegue il metodo che ritiene opportuno.

- Mediator ☑ - Permette di semplificare la comunicazione tra istanze di varie classi, riducendo le dipendenze cicliche. Il mediatore incapsulerà gli oggetti del sistema, e verranno rimosse le dipendenze cicliche tra le componenti.

- Memento ☑ - Incapsula lo stato di un oggetto, in un oggetto di tipo memento. Gli oggetti, tramite `save() : Memento` e `restore(Memento : m)` possono ripristinare lo stato dell'oggetto all'ultimo salvataggio. Banalmente usato per implementare `undo()`, conservando nel client uno storico di stati.
