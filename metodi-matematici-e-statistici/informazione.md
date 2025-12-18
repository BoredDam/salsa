# Elementi di teoria dell'informazione 

È difficile definire l'informazione: esistono tuttavia delle metriche confrontare l'informazione trasportata.

## *A mathematical theory of communication* - Shannon 1948

### Entropia dell'informazione

L'entropia è
- qualcosa che cresce nel tempo (l'informazione non va indietro)
- disordine di un sistema
- una misura dell'incertezza
- la quantità di informazione contenuta in una variabile (o una misura d'ignoranza).

#### Esempio

Ho un mazzo di carte in mano: lo lancio. Le carte non sono più in ordine, e non so più dove sono le carte. 

> L'entropia è definita come la quantità di informazione che posso codificare in un bit.

### Formula dell'entropia
Shannon introduce una funzione per misurare l'entropia, ossia:

$$
I(p) = -p\log_2 (p) = p\log_2\left(\frac{1}{p}\right)
$$

con $p = $ probabilità dell'evento studiato. 

### Proprietà dell'entropia dell'informazione

1. $I(1) = 0$
2. $I(p) \geq 0$
3. $I(p) \leq I(q) \qquad \text{se } p > q$
4. $I(pq) = I(p) + I(q)$

Il logaritmo gode di tutte queste proprietà.

## Ogni distribuzione ha un'entropia

Calcoliamo l'entropia per la Bernoulli: un solo lancio, due esiti equiprobabili.
- $P(1) = p$
- $P(0) = 1 - p$

$$
I(p) = \sum_{i=1}^{2} -p_i\log(p_i) = -p\log(p) -(1-p)\log(p)
$$

Sostituendo

$$
I(1/2) = -\log_2(1/2) = -\log_2(2^{-1}) = 1 
$$

Entropia massima, incertezza massima. Informazione maggiore, più predittibilità.


Osserviamo che $I(0) = 0$ e $I(1) = 0$.


## Teorema

Se ho $m$ esiti con probabilità $p_1, p_2, \dots, p_m$.

$$
I(p_1, p_2, \dots, p_m) \geq I\left(\frac{1}{m}, \dots, \frac{1}{m}\right)
$$


## Applicazioni del principio della massima entropia

Non so nulla del mio sistema. Assumere la distribuzione uniforme è logico e matematicamente corretto, in quanto massimizza l'informazione quando non ci sono vincoli noti.

## *Information Theory and Statistical Mechanics* - Ensemble di Massima Entropia, Jaymes 1957

Immaginiamo di avere un sistema aleatorio, e voglio conoscere la probabilità di osservare i vari risultati. Data l'informazione che osservo, voglio conoscere i valori di $p_i \ \forall i$.

### Esempio: conosco solo il valore medio

Cosa assumo, noto solo il valore medio?

1. Traduco l'informazione in vincoli matematici
2. Massimizzo l'entropia di informazione sotto quei vincoli + il vincolo $\sum_i p_i = 1$

> La Gaussiana massimizza l'informazione, con una varianza finita

## Applicazioni pratiche

### Generazione di chiavi

Scegliere la distribuzione che massimizzi l'informazione delle chiavi generate.

### Quantificare l'informazione trasportata da un'immagine

Tramite delle mappature, si può provare a massimizzare l'informazione dell'immagine. Codifiche entropiche...

### Varie applicazioni nella fisica

