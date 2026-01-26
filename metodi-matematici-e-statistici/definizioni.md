# Recappone (st. pazienza)

## **Evento**

Un evento è una proposizione che può essere vera o falsa

Alcuni eventi noti sono l'evento certo $\Omega$ e l'evento impossibile $\varnothing$.

## **Probabilità**

Sia $(P, \Omega, \mathcal{A})$ uno spazio di probabilità. $\Omega$ insieme di tutti gli eventi, $\mathcal{A} \subseteq \mathcal{P}(\Omega)$ e $P: \mathcal{A} \to [0,1]$ misura di fiduciosità dell'evento.

$$
P(\Omega) = 1,\quad P(A) \geq 0 \quad \forall A \in \mathcal{A}
$$

## **Probabilità condizionata**

$$
P(B|A) = \text{Probabilità di $B$ noto $A$}
$$

In particolare, se i due eventi sono indipendenti, $P(B) =  P(B|A)$

$$
P(B|A) = \frac{P(B \cap A)}{P(A)}
$$

### **Teorema di Bayes**

Il teorema di Bayes afferma che, con $A,B \in \mathcal{A}$ con $P(A), P(B) > 0$.

$$
P(B|A) = \frac{P(B \cap A)}{P(A)} \qquad P(A|B) = \frac{P(A \cap B)}{P(B)} \Rightarrow P(A|B)P(B) = P(A \cap B)
$$

e quindi

$$
P(B|A) = \frac{P(A|B)P(B)}{P(A)}
$$

## **Teorema della probabilità totale**

Se $A_i,A_j \in \mathcal{A}$ sono disgiunti, allora
$$
P(B) = \sum_{i=1}^n P(B|A_i)P(A_i)
$$

## **Coefficiente Binomiale** (yes im this idiotic)

$$
\binom n k = \frac{n!}{k!(n-k)!}
$$

## **Variabili aleatorie (discrete)**

Sono applicazioni $X: \Omega \to \mathbb{R}$ tali che $\{X \leq t\} \in \mathcal A$

Quando l'insieme $X(\Omega)$ è enumerabile o finito, la variabile aleatoria si dice discreta, altrimenti si dice continua.

### **Distribuzione** o **legge**

Con $A \subset \mathbb{R}$ qualsiasi sotto insiemi dei numeri reali

$$
P(X \in A) \quad\forall A \in \mathbb R
$$

è la distribuzione di $X$

### **Densità**

### **Funzione di ripartizione**

### **Speranza matematica**

### **Momento di ordine $k$**

### **Momento centrato di ordine $k$**

### **Varianza e covarianza**

$$
\sigma^2 =\text{Var}(X) = E[(X - E[X])^2]
$$

$$
\text{Cov}(X,Y) = E[(X - E[X])(Y - E[Y])]
$$

Notiamo che $\text{Cov}(X,X) = \text{Var}(X)$

### **Deviazione standard**

$$
\sigma = \sqrt{\sigma^2}
$$


## **Legge dei grandi numeri**

Campionando da un insieme di variabili aleatorie con media $\mu$, al crescere del numero di campioni, la differenza tra la media campionaria e la media teoria si riduce.

$$
\lim_{n\to+\infty} P(|\overline{X}_n - \mu| > \eta) = 0 \qquad \forall \eta > 0
$$

ossia $\overline{X}_n \xrightarrow{\mathcal P} \mu$

## **Teorema del limite centrale**

Data una successione di variabili aleatorie $X_n$ con media $\mu$ e varianza $\sigma^2$, la variabile aleatoria normale standardizzata

$$
S_n =\frac{\overline X_n - \mu}{\sigma}\sqrt n
$$

converge a $S \sim N(0,1)$. Possiamo usarla su campioni $n \geq 30$, e con le binomiali se $np \geq 5$ e $n(1-p) \geq 5$.

## **Statistica descrittiva - nozioni utili**

- Range o variabilità, $\max X - \min X$
- Frequenze assolute e frequenze relative (non normalizzate e normalizzate)
- Frequenze relative cumulative (approssima la $F_X(t)$ funzione di ripartizione)
- Media $\overline X$
- Moda: valore più frequente
- Mediana: divide l'insieme di dati in due gruppi di eguale dimensione (se l'insieme è pari, si prende la media tra i due valori centrali)
- Quantili di ordine $k$: dividono i $k-1$ valori che suddividono i dati in $k$ gruppi
- Varianza empirica
- Deviazione standard empirica
- Momento empirico centrato di ordine $r$, indicato con $\mu_r$
- Skewness, che quantifica la asimmetria della distribuzione: 
$$
\gamma_1 = \frac{\mu_3}{(\mu_2)^{\frac{3}{2}}}
$$
- Curtosi, che quantifica quanto è spanciata la distribuzione:
$$
\beta_2 = \frac{\mu_4}{\mu_2^2}
$$

Sulla curtosi, nota la legge dei tre sigma, nella distribuzione normale $\beta_2 = 3$

- Coefficiente di curtosi, che esprime la spanciatezza in funzione di quella della gaussiana:
$$
\gamma = \beta_2 - 3
$$

## **Statistica**

Una funzione di variabili aleatorie è detta statistica.

## **Stimatori**

Una statistica $\hat\theta$ a valori nell'immagine di $\theta$ è detta stimatore puntuale di $\theta$.

## **Stimatore non distorto**

Uno stimatore $\hat\theta$ è detto stimatore non distorto se

$$
E[\hat\theta] = \theta
$$

In particolare:

- Lo stimatore non distorto della media è la media campionaria
- Lo stimatore non distorto della varianza, nota la media, è la varianza campionaria
- Lo stimatore non distorto della varianza, non nota la media, è la varianza campionaria misurata usando la media campionaria, e moltiplicandola per $\frac{n}{n-1}$ (altrimenti sarebbe distorto, in quanto sottostimerebbe la varianza).

## **Test d'ipotesi**

È un processo che permette di fare delle ipotesi su una popolazioni (media, varianza) e utilizzare un campione per testare l'ipotesi.

1. Crea le ipotesi. $H_0$ è l'ipotesi nulla (ciò che assumiamo), $H_1$ è l'ipotesi alternativa, che è ciò che testiamo sulla popolazione. 
$H_0$ è l'opposto di $H_1$, anche se non hanno ruoli simmetrici.

2. Il campione deve essere effettuato in maniera opportuna. Ad esempio, $n\geq30$ permette di usare una normale.

3. 


Ad esempio. Vogliamo verificare l'ipotesi nulla $H_0$ che il reddito medio di una popolazione sia $\mu \geq 70k$.

Campioniamo dalla popolazione, ottenento una media campionaria $\overline X = 65 k$. È abbastanza da dimostrare che l'ipotesi nulla sia errata? Forse! Calcoliamo la probabilità di ottenere una media campionaria di $\overline X = 65$ da un campione con $\mu= 70k$

## **Coefficiente di correlazione lineare**

$$
\rho = \frac{\sigma_{xy}}{\sigma_x\sigma_y} = \frac{\text{Cov}(X,Y)}{\sqrt{\text{Var}(X)\text{Var}(Y)}}
$$

$|\rho| \leq 0.3$ correlazione debole, $0.3 < |\rho| \leq 0.7$ correlazione moderata, $ 0.7 < |\rho| \leq 1$ correlazione forte.

## **Coefficiente di determinazione**

$$
R = \frac{\text{Cov}(X,Y)^2}{\text{Var}(X)\text{Var}(Y)} = \rho^2
$$


## **Processo stocastico**

Famiglia di variabili aleatorie che dipendono da $t \in T$. $(X_t)_{t \in T}$.

Il parametro $t$ può essere visto come un indice temporale.
Se $t$ è continua, allora si ha un **processo a tempo continuo**, altrimenti **a tempo discreto**.

## **Catene di Markov**

Sono un processo stocastico a tempo discreto che gode della proprietà di mancanza di memoria. $X_t$ può passare tra vari stati appartenenti all'insieme $E$. Il passaggio da uno stato all'altro a tempo $t+1$, dipende esclusivamente dallo stato a tempo $t$.

La matrice di transizione $P(t)$ contiene al suo interno la probabilità all'istante $t$ di passare da uno stato $i \to j$, con $i$ alle righe e $j$ alle colonne.

Nelle catene di markow

- $i$ **comunica** con $j$ se esiste un numero di passi $m \geq 0$ per cui la probabilità di andare da $i$ a $j$ è $p^{(m)}_{ij}\geq 0$, non vale la simmetria ma vale la proprietà transitiva

- Una **classe chiusa** $C \subset E$ è un insieme di stati $C$ che non comunica con $C \backslash E$

- Una classe chiusa si dice **irriducibile** se tutti i suoi stati comunicano

- Se una classe chiusa è costituita da uno stato, questo si dirà **assorbente**

- Se uno stato si dice **ricorrente** se ho la certezza di ritornare, ad un certo tempo $t$, allo stato stesso. Uno stato non ricorrente si dice **transitorio**

Una catena di Markov è irriducibile se tutti gli stati sono o tutti transitori o tutti ricorrenti, ma per essere fatta da iptutti transitori, la catena dovrebbe essere infinita.

Per calcolare la probabilità di arrivare ad uno stato in $m$ passi, basta calcolare

$$
w = vP^{(m)}
$$

## **Distribuzioni stazionarie**

Una distribuzione $v$ si dice stazionaria se

$$
v = vP
$$