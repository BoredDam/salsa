# Utils for lab

## Varianza e Covarianza

Con $\overline{x} = Media(X)$
$$
Cov(X,Y) = \frac{1}{N}\sum_{i=1}^N (x_i - \overline{x})(y_i - \overline{y})
$$

$$
Var(X) = Cov(X,X) = \frac{1}{N}\sum_{i=1}^N (x_i - \overline{x})^2
$$


```py
def cov(X,Y):
    N = len(X)
    return np.sum((X-np.mean(X))*(Y-np.mean(Y)))/N

def var(X):
    return cov(X,X)
```

## Coefficiente di correlazione lineare

$$
correlation = \frac{\overline\sigma_{xy}}{\overline\sigma_x\overline\sigma_y} = \frac{Cov(X,Y)}{\sqrt{Var(X)Var(Y)}}
$$

```py
def corr(X,Y):
    return cov(X,Y)/np.sqrt(var(X)*var(Y))
```


## Regressione lineare e metodo dei minimi quadrati

La retta dei minimi quadrati sarà data da
$$
y = b_0 + b_1x
$$

Dove 
$$
b_0 = \overline{y} - \frac{Cov(X,Y)}{Var(X)} \overline{x}
$$

$$
b_1 = \frac{Cov(X,Y)}{Var(X)}
$$


```py
b0 = np.mean(Y) - (cov(X,Y)/var(X)) * np.mean(X)

b1 = cov(X,Y)/var(X)

def linear_reg(X, b_1, b_0):
    lin_reg = []
    for x in X:
        lin_reg.append(x*b_1 + b_0)
    return lin_reg
```

## Coefficiente di determinazione

$$
R = \frac{Cov^2(X,Y)}{Var(X)Var(Y)}
$$