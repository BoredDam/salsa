# Esercizi


## Problema 1 - Molle

> Abbiamo una molla. Alla fine della molla c'è un punto materiale di massa $m$. All'inizio del moto, il punto è in posizione $x \neq \text{posizione di equilibrio}$. La costante elastica della molla è $K = 28400 \frac{N}{m}$. Il punto $X = 0.1 m$ dall'origine e la massa $m = 1000 kg$.

### 1.1 Calcola la legge oraria
Sul punto materiale agisce una forza pari a

$$
F = -k \Delta x
$$
$$
ma = -k\Delta x
$$
$$
x''(t) = -\frac{k}{m}x(t) = -\omega^2 x(t) \implies
$$
$$
\implies \omega = \sqrt{\frac{k}{m}}
$$

Poniamo $x(t) = A\cos(wt + \phi)$, quindi $x'(t) = -\omega A\sin(wt + \phi)$.

Otteniamo il seguente problema di Cauchy

$$
\begin{cases}
x'(0) = 0\\
x(0) = X
\end{cases}
$$

e quindi

$$
\begin{cases}
\sin\phi = 0 \implies \phi = 0\\
A\cos\phi = X \implies A = X
\end{cases}
$$

otteniamo come legge oraria

$$
x(t) = X\cos(wt)
$$

### 1.2 Calcoliamo energia potenziale e cinetica

In generale l'energia potenziale elastica $U_\text{elastica} = \frac{1}{2}k(\Delta x)^2$. 

L'energia cinetica, all'istante 0, è uguale a 0.

$$
E_m (t=0) = \frac{1}{2}kX^2 + 0
$$

$$
E_m (t=t_\text{eq}) = \frac{1}{2}kX^2 + 0
$$

L'energia meccanica si conserva, quindi è uguale all'inizio e alla fine.

Possiamo anche esplicitamente calcolare la velocità e poi la'energia cinetica, ma sappiamo che come **come in ogni moto armonico**, la posizione di energia potenziale minima è quella di equilibrio.

### 1.3 Quanta forza applicare per mantenere la molla in tensione?

L'opposto della forza elastica.

$$
F_\text{el} = -kx
$$

quindi $F = kx$.


## Problema 2 - Molla in verticale
> Abbiamo un punto materiale di massa $m = 300 g$, attaccato ad una molla in verticale, con una costante $K = 50 N/m$. 

### 2.1 Trovare il valore di $x$ elungazione della molla tale che il sistema è in equilibrio.

Poniamo il sistema di riferimento sul punto materiale. Le forze che agiscono sul punto materiale sono la forza elastica e la forza gravitazionale.

Poniamo la somma delle forze uguale a zero, in quanto il sistema è in equilibrio.

$$
ma = - mg - kx = 0
$$

$$
-mg = kx
$$ 

$$
-\frac{mg}{k} = x
$$

La domanda chiede l'elungazione della molla, quindi prendiamo il valore assoluto 

$$
x = \left| -\frac{mg}{k}\right| =\frac{mg}{k}
$$

### 2.2 Energia potenziale elastica della molla

$$
U_\text{elastica} = \frac{1}{2}k(\Delta x)^2
$$

$$
\implies U_\text{elastica} = \frac{1}{2}k \left(\frac{mg}{k}\right)^2
$$

$$
\implies U_\text{elastica} = \frac{m^2g^2}{2k}
$$

### 2.3 Frequenza dell'oscillazione

$$
\omega^2 = \frac{k}{m}
$$

$$
\omega = \sqrt{\frac{k}{m}}
$$

## Problema 3 - Velocità di fuga dai corpi

> Dato un corpo di massa $M = 1.2 M_{\odot}$ e raggio $R = 10 km$. Trovare la velocità di fuga.

>> *La velocità di fuga è la velocità per cui un punto materiale arriva a distanza infinita dal corpo di massa $M$ a velocità nulla*. 

Poniamo come condizione la **conservazione dell'energia meccanica**, quindi $E_m(t=0) = E_m(t=t_f)$.

$$
F_\text{grav} = - G\frac{M m}{r^2} 
$$

l'energia potenziale gravitazionale è pari a 

$$
U_\text{grav} = - G\frac{M m}{r} 
$$

$$
E_m = \frac{1}{2}mv^2 - G\frac{Mm}{r} = \frac{1}{2}mv_0^2 = 0 \qquad \text{in quanto cerchiamo la velocità minima}
$$

[...] completa a casa

## Problema 4 -

> Un satellite va a $v_0$ vicino al pianeta Terra di massa $M_T$. Il punto più vicino alla Terra della traiettoria di questo satellite è a distanza $d_1$. La massa del satellite è $m = 2560$, la velocità a cui viaggia è $v_0 = 5432 m/s$.

$$
E_m(d_0) = \frac{1}{2}mv_0^2 - G\frac{M_T m}{d_0} \qquad \text{poniamo} \quad d_0 >> R
$$

$$
= \frac{1}{2}mv_0^2 \qquad \qquad \qquad
$$

$$
E_m(d_1) = \frac{1}{2}mv^2 -G \frac{M_Tm}{d_0} = \frac{1}{2}mv_0^2
$$

Arriviamo quindi a dire

$$
\frac{1}{2}mv^2 = \frac{1}{2}mv_0^2 + G \frac{M_Tm}{d_0}
$$

$$
\frac{1}{2}v^2 = \frac{1}{2}v_0^2 + G \frac{M_T}{d_0}
$$

$$
v^2 = v_0^2
$$

## Problema 5

> Stima l'energia potenziale gravitazionale media, sapendo la distanza media tra due stelle. Le due stelle hanno massa $M = 30 M_\odot$.

$$
U = -G\frac{M_1M_2}{r} = -G\frac{M^2}{r}
$$

$$
\langle U \rangle = -\langle\frac{GM^2}{r} \rangle \approx -\frac{GM^2}{\langle r\rangle} = -\frac{GM^2}{r_\text{media}} 
$$

## Problema 6 - Urti

### Introduzione agli urti

Dobbiamo escludere totalmente la cinematica, e affidarci solo alla dinamica.
```
O --->  <--- O
```

- Anaelastico: l'energia cinetica non si conserva, ma si dissipa.
- Elastico: l'energia cinetica si conserva.

La quantità di moto si conserva in entrambi i casi. La quantità di moto è definita come

$$
\vec{P} = m \vec{v}
$$

prendiamo la quantità di moto del sistema

$$
\vec{P}_{tot} = m_1 \vec{v}_1 + m_2 \vec{v}_2 + \dots + m_n \vec{v}_n
$$

Questa somma è costante in qualsiasi istante del problema, in quanto 

$$
\frac{dP_\text{tot}}{dt} = F = 0
$$

### 1.1 Urto anaelastico

> Trovare la velocità finale successiva ad un urto anaelastico tra due corpi $m_1, m_2$. $m_2$ è fermo, $m_1$ viagga a velocità $v$.

```
^
|  m_1    v        m_2
|   o - - - >   O
--------------------->
```

```
^
|           m_1 + m_2  v_f
|               oO - - - >
--------------------->
```

Abbiamo due corpi di massa $m_1, m_2$.

$$
P_\text{iniziale} = m_1 \cdot v = P_\text{finale} = (m + M) v_f
$$

$$
v_f = \frac{m}{m + M} v
$$

### 1.2 Urto elastico

$$
\begin{cases}
mv = mv_f + MV_f\\
\frac{1}{2}mv^2 = \frac{1}{2}mv_f^2 + \frac{1}{2}MV_f^2
\end{cases}
$$

$$
\begin{cases}
mv = mv_f + MV_f\\
mv^2 = mv_f^2 + MV_f^2
\end{cases}
$$

[...]

$$
v_f^2 - v^2 + \frac{m}{M}v_f^2 + \frac{m}{M}v^2 -2\frac{m}{M}vv_f = 0
$$

$$
v_f^2(1 + \frac{m}{M}) - \frac{2mv}{M}v_f + v^2(\frac{m}{M} - 1) = 0
$$

$$
v_f^2(M + m) -2mvv_f + v^2(m-M) = 0
$$

$$
\text{ricordiamo che $v$ è fissato}
$$

$$
v_{f_{1,2}} = \frac{2mv \pm \sqrt{4m^2v^2 - 4(m^2-M^2)v^2}}{2(M+m)}
$$

$$
v_{f_{1,2}} = \frac{2mv \pm 2MV}{2(M+m)}
$$

$$
v_{f_{1}} = \frac{2mv + 2mV}{2(M+m)} \quad \text{velocità se l'urto non avviene (in quanto uguale a $v$)}\\
$$

$$
v_{f_{2}} = \frac{2mv - 2mV}{2(M+m)} \text{velocità se l'urto avviene}
$$

notiamo che se le masse sono uguali, la velocità si trasferisce totalmente sull'altro corpo.
