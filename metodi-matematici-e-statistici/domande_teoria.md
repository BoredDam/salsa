# Domande di teoria metodi

## Dare la definizione assiomatica di probabilità, avendo cura di definire anche gli spazi di probabilità.

Definiamo spazio di probabilità $(P, \Omega, \mathcal{A})$ la terna costituita da
- $\Omega$ insieme di tutti gli eventi
- $\mathcal A \subseteq \mathcal P (\Omega)$ sottoinsieme dell'insieme delle parti di $\Omega$ con gli eventi possibili
- $P$ funzione che quantifica la fiduciosità di un evento $A \in \mathcal A$

Definiamo quindi probabilità proprio la funzione

$$
P: \mathcal A \to [0,1]
$$

tale che $P(\Omega) = P(\text{"avviene un evento qualsiasi"})= 1$, e che $P(A) \geq 0 \ \forall A \in \mathcal A$ 

## Dare la definizione di variabile aleatoria. Qual è la differenza tra variabile aleatoria discreta e continua?

Una variabile aleatoria è una funzione X: $\Omega \to \mathbb{R}$ tale che $\forall t \in \mathbb{R},  \{\omega: X(\omega)\leq t\} \in \mathcal{A}$, ossia è un evento possibile.

In altre parole, una variabile aleatoria è un'applicazione che associa ad un evento un valore in $\mathbb{R}$, e permette di usare strumenti matematici su quelli che sono in realtà eventi (gli eventi sono proposizioni vere o false, non nascono come numeri come si potrebbe pensare con il lancio di un dado o dallo studio di una popolazione).

Una variabile aleatoria $X$ si dice continua se $X(\Omega)$ non è enumerabile, mentre si dice discreta se $X(\Omega)$ è finito o enumerabile.

## Sia X una variabile aleatoria discreta. Dare la definizione di legge di X e di densità discreta.

La legge è $P(X \in A)$ con $A \subset \mathbb R$. È una funzione che associa a tutti i valori in un sottoinsieme dei reali (codominio delle variabili aleatorie) la loro probabilità.

La densità discreta è la funzione $p(x) = P(X=x)$ con $x \in \mathbb R$.

## Di che proprietà gode la densità discreta?

La densità discreta gode delle seguenti proprietà

- $\forall x \in \mathbb R$, $p(x) \geq 0$. 

- $\sum_{x \in \mathbb R} p(x) = 1$


## Sia data una catena di Markov. Dare la definizione di matrice di transizione.

La matrice di transizione di una catena di Markov esprime la probabilità, all'istante $t$, di passare da uno stato $i$ allo stato $j$.

$$
p_{ij} = P(X_{t+1} = j | X_{t} = i)
$$


## Dare la definizione di catena di Markov irriducibile.

Una catena di Markov si dice irriducibile se gli stati sono o tutti transitori o tutti ricorrenti. In una catena di Markov irriducibile finita, gli stati devono essere tutti ricorrenti.


In generale, una classe (o una catena) si dice irriducibile se tutti i suoi stati comunicano.


## Dare la definizione di stimatore

Definiamo uno stimatore di $\theta$ una statistica $\hat\theta$ (ovvero una funzione di variabili aleatorie) a valori nell'immagine di $\theta$.

## Dare la definizione di stimatore non distorto

$\hat\theta$ è uno stimatore non distorto di $\theta$ se

$$
E[\hat\theta] = \theta
$$


## Quale stimatore usereste per stimare la varianza di una distribuzione con media nota?

La varianza campionaria con media nota è uno stimatore della varianza non distorto.

$$
\hat{\sigma^2} = \frac{1}{n}\sum_{i=1}^n(X_i - \mu)^2
$$


## Dimostrare che lo stimatore scelto al punto precedente è non distorto

Il nostro campione $X$ è costituito da variabili aleatorie $X_i$ con media $\mu$ e varianza $\sigma^2$

$$
E[\frac{1}{n}\sum_{i=1}^n(X_i - \mu)^2] = \frac{1}{n}\sum_{i=1}^n E[(X_i - \mu)^2]
$$

$$ 
 = \frac{1}{n}\sum_{i=1}^n E[(X_i - \mu)^2] = \frac{1}{n} n \sigma^2 = \sigma^2
$$


## Dare la definizione di processo stocastico

Un processo stocastico è una famiglia di variabili aleatorie che dipendono dallo stesso parametro $t \in T$.

$$
\{X_t\}_{t\in T}
$$

Dove $t$ può essere interpretato come un indice temporale da un insieme $T$ discreto o continuo.

## Dare la definizione di catena di Markov

Una catena di Markov è un processo stocastico che gode della proprietà di assenza di memoria, ossia la probabilità dello stato successivo dipende esclusivamente dallo stato attuale.

## Dare la definizione di classe chiusa

In una catena di Markov, una classe $C$ si dice chiusa se tutti gli stati non comunicano con gli stati di $E \backslash C$.

## Dare la definizione di evento

Un evento $E$ è una proposizione, che può essere vera o falsa, come $E=\text{"è uscita testa"}$ o $E=\text{"è uscita croce"}$. Alcuni eventi particolari sono 
- $\Omega$ evento certo: una proposizione sempre vera
- $\varnothing$ evento impossibile: una proposizione sempre falsa

## Dare la definizione di evento incompatibile

Due eventi $A$ e $B$ se non possono essere mai entrambi veri o entrambi falsi. L'avvenire di uno esclude l'avvenire dell'altro, come nel risultato del lancio di una moneta.

$A \implies \lnot B, \quad B \implies \lnot A$


## Dati i due eventi A = "Giorgino ha studiato" e "B = Giorgino ha passato l’esame", esprimere in termini di A e B l’evento composto E = "Giorgino non ha passato l’esame e ha studiato"

$$
E = B^c \land A
$$

## Sapendo che gli eventi A e B sono indipendenti e sapendo che P(A) = 0.3, P(B) = 0.5 calcolare la probabilità dell’evento E.

La probabilità che avvenga l'unione di due eventi disgiunti è data dal prodotto delle loro probabilità.

$P(B^c) = 1 - P(B) = 0.5$

$P(E) = P(B^c) P(A) =  0.5 \cdot 0.3 = 0.15$

## Descrivere la distribuzione geometrica e il suo legame con la distribuzione binomiale

La distribuzione geometrica modella fenomeni aleatori che hanno esiti di tipo successo/insuccesso, con un focus sul tempo di primo successo (indicato con $x$). Gode della proprietà di assenza di memoria, per cui il primo successo non dipende in alcun modo dagli ultimi esiti.

La distribuzione binomiale modella fenomeni aleatori con esiti del tipo successo/insuccesso, con un focus sulla probabilità di ottenere un numero $x$ di successi in $n$ esperimenti.

Conoscere il tempo di primo successo, significa conoscere anche il tempo di ultimo fallimento.

$T$ è una variabile aleatoria che conta il tempo di primo successo, e vogliamo contare $P(T = n)$

Con $x=0$
$$
P(T > n) = \binom{n}{x}p^x(1-p)^{(n-x)} = \binom{n}{0}(1-p)^{n} = (1-p)^{n} 
$$

$$
P(T > n-1) = \binom{n-1}{0}(1-p)^{n-1} = (1-p)^{n-1} 
$$

Ora, $P(T > n - 1) - P(T > n) = P(T=n)$, quindi

$$
(1-p)^{n-1} - (1-p)^{n} = p(1-p)^{n-1} 
$$

Ottenendo la nota distribuzione geometrica.


## Dare la definizione di convergenza in probabilità.

Una successione $(X_n)_{n\in\mathbb N}$ converge in probabilità a $X$ se

$$
\lim_{n \to +\infty} (|X_n - X| \geq \eta) = 0, \quad \forall \eta > 0
$$

## Enunciare la legge dei grandi numeri

$$
\lim_{n \to +\infty} (|\overline{X}_n - \mu| \geq \eta) = 0, \quad \forall \eta > 0
$$

## Assumendo vera la disuguaglianza di Chebishev dimostrare la legge dei grandi numeri.

La disuguaglianza di Cebisev afferma che:

$$
(|X - E[X]| \geq \eta) \leq \frac{\text{Var}(X)}{\eta^2}, \quad \forall \eta > 0
$$

Sostituendo $X$ con $\overline{X}_n$, otteniamo che

$$
(|\overline{X}_n - E[\overline{X}_n]| \geq \eta) \leq \frac{\text{Var}(\overline{X}_n)}{\eta^2}, \quad \forall \eta > 0
$$

Calcoliamo

$$
E[\overline{X}_n] = E[\frac{1}{n}\sum_{i=1}^n\overline{X}_i] = \frac{1}{n}\sum_{i=1}^n E[\overline{X}_i] = \mu
$$


$$
\text{Var}(\overline{X}_n) = \text{Var}(\frac{1}{n}\sum_{i=1}^n \text{Var}(X_i)) =
$$

$$
= \frac{1}{n^2}\sum_{i=1}^n \text{Var}({X}_i) = \frac{n\sigma^2}{n^2} = \frac{\sigma^2}{n}
$$

Concludiamo che 

$$
(|\overline{X}_n - \mu| \geq \eta) \leq \frac{\sigma^2}{n\eta^2}, \quad \forall \eta > 0
$$

Osserviamo che ponento $n\to+\infty$

$$
\lim_{n\to+\infty} (|\overline{X}_n - \mu| \geq \eta) = 0, \quad \forall \eta > 0
$$

Come volevasi dimostrare.

## Come si applica in pratica?

La legge dei grandi numeri stabilisce che, all'aumentare del numero di campioni, i risultati campionari si avvicinano alla teoria, ottenendo via via risultati più accurati.

Ad esempio, immaginiamo di campionare un numero crescente di monete non truccate

```
0                   P(M=1)=0
01                  P(M=1)=0.5
010                 P(M=1)=0.25
010111              P(M=1)=0.66
01011001001001010 ... P(M=1)=0.5
```

al crescere del numero dei campioni, la media campionaria si avvicina sempre più alla speranza matematica.

## Dare la definizione di funzione di ripartizione, sia nel caso discreto che nel caso continuo.

Discreta, con $p(x)$ densità discreta:

$$
F_X(t) = \sum_{x \leq t} p(x)
$$


Continua, con $f(x)$ densità:

$$
F_X(t) = \int_{-\infty}^t f(x)
$$

## Spiegare a parole il significato di tale funzione.

La funzione di ripartizione fornisce una funzione di probabilità cumulativa per tutti i valori della variabile aleatoria minori o uguali a $t$. Permettono di ottenere la probabilità di non superare (o superare, col complementare) un valore soglia. Nel mondo delle variabili aleatorie cotntinue sono particolarmente importanti, in quanto i singoli valori della v.a. hanno probabilità $\to 0$.

## Dare la definizione di quantile di ordine $\alpha$ e spiegare il legame con la funzione di ripartizione.

Il quantile di ordine $\alpha$ è il valore più grande della variabile aleatoria che divide l'area sottesa in due parti di area $\alpha$ e $1-\alpha$. Sembra quasi un'inversa della funzione di ripartizione, ed effettivamente...

$$
q_{\alpha} = \sup\{r \in \mathbb R: F_X(r) = \alpha\}
$$

## Esprimere in formule la probabilità che $X$ assuma valori in un intervallo $[a, b]$ esplicitando il legame con la funzione di ripartizione.

$$
P(a \leq X \leq b) = ... = 
P(a < X < b) = 
$$
$$
= P(X < b) - P(X < a) = F_X(b) - F_X(a)
$$

