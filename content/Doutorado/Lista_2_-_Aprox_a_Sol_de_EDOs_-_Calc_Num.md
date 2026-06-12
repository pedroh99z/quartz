---
title: Lista 2 - Aproximação a Soluções de EDOs - Cálculo Numérico
---

1. Utilizando o método de Taylor de ordem 2:

a)  Resolva $$\left\{\begin{matrix}
        y' &=& -xy + \frac{1}{y^2}\\
        y(1) &=& 1
    \end{matrix}\right.$$ de $x = 1$ para $x=2$ e passo $h = 0.25$.

b)  Resolva $$\left\{\begin{matrix}
        y' &=& \frac{1}{x^2} - \frac{y}{x} - y^2\\
        y(1) &=& -1
    \end{matrix}\right.$$ de $x = 1$ para $x=2$ e passo $h = 0.25$.



2. Utilizando o método de Euler:

a)  Resolva $$\left\{\begin{matrix}
        y' &=& x + y\\
        y(0) &=& 1
    \end{matrix}\right.$$ de $x = 0$ para $x=1$ e passo $h = 0.25$.

b)  Resolva $$\left\{\begin{matrix}
        x y' &=& x - y\\
        y(2) &=& 2
    \end{matrix}\right.$$ de $x = 2$ para $x=3$ e passo $h = 0.25$.



3. Utilizando o método de Euler modificado:

a)  Resolva $$\left\{\begin{matrix}
        y' + y &=& e^{-x}\\
        y(0) &=& 0
    \end{matrix}\right.$$ de $x = 0$ para $x=1$ e passo $h = 0.25$.

b)  Resolva $$\left\{\begin{matrix}
        y' &=& \frac{1}{x^2} - \frac{y}{x} - y^2\\
        y(1) &=& -1
    \end{matrix}\right.$$ de $x = 1$ para $x=3$ e passo $h = 0.5$.



4. Resolva $$\left\{\begin{matrix}
    y' &=& -2 y\\
    y(0) &=& 1
\end{matrix}\right.$$ de $x = 0$ para $x = 2$, com $h = 0.5$,
utilizando:

a)  Runge-Kutta de 3ª Ordem;

b)  Runge-Kutta de 4ª Ordem.



5. Reescreva os seguintes problemas de 2ª ordem como problemas de 1ª ordem:

a)  $$\left\{\begin{matrix}
        y'' &=& 2 (e^{2x} - y^2)^{1/2}\\
        y(0) &=& 0\\
        y'(0) &=& 1
    \end{matrix}\right.$$

b)  $$\left\{\begin{matrix}
        y'' &=& 2y^{3}\\
        y(1) &=& 1\\
        y'(1) &=& -1
    \end{matrix}\right.$$




# Gabarito



Exercício 1:

a)

|          | $i = 0$ | $i = 1$ |  $i = 2$  | $i = 3$  |  $i = 4$  |
| :------: | :-----: | :-----: | :-------: | :------: | :-------: |
|  $x_i$   |   1.0   |  1.25   |    1.5    |   1.75   |    2.0    |
| $y(x_i)$ |  -1.0   | -0.8125 | -0.677508 | -0.57465 | -0.492948 |

b\)

|          | $i = 0$ | $i = 1$ | $i = 2$  | $i = 3$  | $i = 4$  |
| :------: | :-----: | :-----: | :------: | :------: | :------: |
|  $x_i$   |   1.0   |  1.25   |   1.5    |   1.75   |   2.0    |
| $y(x_i)$ |   1.0   |  0.875  | 0.768392 | 0.695018 | 0.645923 |



Exercício 2:    

a)

|          | $i = 0$ | $i = 1$ | $i = 2$ | $i = 3$ | $i = 4$ |
| :------: | :-----: | :-----: | :-----: | :-----: | :-----: |
|  $x_i$   |   0.0   |  0.25   |   0.5   |  0.75   |   1.0   |
| $y(x_i)$ |   1.0   |  1.25   |  1.625  | 2.15625 | 2.88281 |

b\)

|          | $i = 0$ | $i = 1$ | $i = 2$ | $i = 3$ | $i = 4$ |
| :------: | :-----: | :-----: | :-----: | :-----: | :-----: |
|  $x_i$   |   0.0   |   0.5   |   1.0   |   1.5   |   2.0   |
| $y(x_i)$ |   2.0   |   1.0   |  0.75   |  0.875  | 1.1875  |



Exercício 3:    

a)

|          | $i = 0$ | $i = 1$ | $i = 2$  | $i = 3$  | $i = 4$  |
| -------- | ------- | ------- | -------- | -------- | -------- |
| $x_i$    | 0.0     | 0.25    | 0.5      | 0.75     | 1.0      |
| $y(x_i)$ | 0.0     | 0.1911  | 0.298126 | 0.348819 | 0.362784 |

b\)

|          | $i = 0$ |  $i = 1$  |  $i = 2$  |  $i = 3$  |  $i = 4$  |
| :------: | :-----: | :-------: | :-------: | :-------: | :-------: |
|  $x_i$   |   1.0   |    1.5    |    2.0    |    2.5    |    3.0    |
| $y(x_i)$ |  -1.0   | -0.618056 | -0.425586 | -0.306965 | -0.225632 |



Exercício 4:    

a)

|          | $i = 0$ | $i = 1$  | $i = 2$  | $i = 3$  |  $i = 4$  |
| :------: | :-----: | :------: | :------: | :------: | :-------: |
|  $x_i$   |   0.0   |   0.5    |   1.0    |   1.5    |    2.0    |
| $y(x_i)$ |   1.0   | 0.333333 | 0.111111 | 0.037037 | 0.0123457 |

b\)

|          | $i = 0$ | $i = 1$ | $i = 2$  |  $i = 3$  |  $i = 4$  |
| :------: | :-----: | :-----: | :------: | :-------: | :-------: |
|  $x_i$   |   0.0   |   0.5   |   1.0    |    1.5    |    2.0    |
| $y(x_i)$ |   1.0   |  0.375  | 0.140625 | 0.0527344 | 0.0197754 |



Exercício 5:    

a) $$\left\{\begin{matrix}
    z' &=& 2 (e^{2x} - y^2)^{1/2}\\
    z (0) &=& 1\\
    y' &=& z\\
    y (0) &=& 0
\end{matrix}\right.$$ b) $$\left\{\begin{matrix}
    z' &=& 2y^{3}\\
    z (1) &=& -1\\
    y' &=& z\\
    y (1) &=& 1
\end{matrix}\right.$$
