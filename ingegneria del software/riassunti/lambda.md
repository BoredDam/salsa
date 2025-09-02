# Funzioni Lambda

Sono delle funzioni anonime. Non sono associate a classi, permettono codice più leggibile, e possono essere passati a metodi.

```
( parameters list ) -> { lambda body }
```
Sono basati sul sistema formale lambda calcolo, definito da Alonzo Church nel 1936.

Offrono **deduzione del tipo degli argomenti** a tempo di compilazione, permettono di omettere parentesi e `return` (è anche offerto un meccanismo di **deduzione del tipo del return**).


```Java
() -> System.out.println("Hello Lambda");
```

```Java
() ->{throw new RuntimeException()}
```

```Java
x -> x+10;
```

```Java
(int x, int y) -> { return x+y; };
```

```Java
(String x, String y) -> x.length() - y.length();
```

```Java
(x, y) -> x.length() - y.length();
```
Se l'ADT dei tipi passati su x e y non dovesse supportare il metodo .length(), avverrà un errore.

## Interfacce funzionali

