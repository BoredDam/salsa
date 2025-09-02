# Streams

L'interfaccia Stream è un'interfaccia che raccoglie operazioni astratte che su flussi e/o aggregati di oggetti. Forniscono dei blocchi funzionali per processare meglio gli aggregati:

- Utilizzano un'iterazione implicita su tutti gli elementi dello stream. Le operazioni scelte vengono applicate su tutto l'aggregato.

- Supportano la programmazione funzionale.

## Elementi di uno stream

- **Source**, da cui vengono presi i dati.
- Una o più **operazioni intermedie**.
- Una **operazione terminale**.

L'operazione source trasforma l'aggregato di oggetti in un oggetto **Stream**. L'invocazione del metodo ``.stream()`` su un aggregato.

Le operazioni intermedie operano su e danno in output **Stream**. Possono essere concatenate in sequenza.

L'operazione terminale può dare in output un aggregato di oggetti o un singolo elemento semplice.

## Creare uno stream

```Java
Stream<Integer> digits = Stream.of(3,2,7,6,5);
Integer[] arr = {};
digits = Stream.of(arr);
```

### Creare uno stream vuoto
```Java
Stream<Integer> digits = Stream.empty();
```

### Creare uno stream da una Collection
```Java
Set<Student> ss = new LinkedHashSet<>();
Stream<Student> stream = ss.stream();
```

### Creare uno stream da un array
```Java
Integer[] digitArray = { 3, 1, 4, 1, 5, 9 };
Stream<Integer> digitStream = Stream.of(digitArray);
```

### Creare uno stream da un File
```Java
Stream<String> stream = Files.lines(path);
```

## Concatenare due stream

```Java
Stream newStream = Stream.concat(stream, stream2);
```

### Generare una sequenza di numeri finita
```Java
IntStream.range(int, int);
IntStream.rangeClosed(int, int);
```


## Streams paralleli e sequenziali

```Java
java.util.stream
List<Student> students = {/*creazione dello stream*/}
Stream stream = students.stream(); // sequential version

Stream parallelStream = students.parallelStream(); // parallel version
```

Gli **streams paralleli** permettono di operare più velocemente su grandi aggregati di dati, distribuendo il lavoro su più thread, non mantenendo l'ordinamento originale dei dati. Meno reliable e prevedibile, in quanto dipende fortemente dal sistema.

Gli **streams sequenziali** sono gli streams di default. Non distribuiscono il lavoro su più thread, mantenendo l'ordinamento.

## Operazioni intermedie sugli streams

- `.filter(Predicate)` esclude tutti gli elementi che non rispettano il predicato.
- `.map(Function)` effettua una trasformazione sugli elementi usando una funzione.
- `.mapToInt`
- `.mapToDouble`
- `.mapToLong`
- `.flatMap(Function)` permette di appiattire streams di stream in uno stream degli elementi contenuti.
- `.peek(Consumer)` effettua un'operazione sugli oggetti dello stream. Una sorta di forEach, ma può essere un'operazione intermedia, in quanto ritorna uno stream.
- `.distinct()` esclude i duplicati
- `.sorted(Comparator)` ritorna uno stream di elementi ordinati. L'ordinamento di default è lessicografico.
- `.limit(long)` ritona i primi n elementi dello stream.
- `.skip(long)` salta i primi n elementi dello stream.

## Operazioni terminali sugli streams

- `Stream.collect(Collectors.toList())` o `Stream.toList()` per passare i dati ad una lista

- `Stream.collect(Collectors.toCollection(TreeSet::new))` per passare i dati ad una collection qualsiasi

- `Stream.collect(Collectors.joining(", "))` per unire gli elementi in una stringa separata da ", ".

- `Stream.collect(Collectors.summingInt(Employee::getSalary))` per ritornare un intero che è somma dei salari dei dipendenti.

- `Stream.collect(Collectors.groupingBy(Employee:getDepartment))` per 

- `Stream.collect(Collectors.groupingBy(Employee:getDepartment, Collectors.summingInt(Employee::getSalary)))`

- `Stream.collect(Collectors.partitioningBy(s -> s.getGrade() >= PASS_THRESHOLD))`


