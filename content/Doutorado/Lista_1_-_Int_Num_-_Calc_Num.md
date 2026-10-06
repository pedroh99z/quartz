---
title: Lista 1 - Integração Numérica - Cálculo Numérico
---



1. Calcule $\int_0^1 x\ sen(x)\ dx$:

a)  por somas de Riemman à esquerda (use $n = 5$);

b)  por somas de Riemman à direita (use $n = 5$);

c)  pela Regra do Ponto Médio (use $n = 5$).

d)  O valor exato desta integral é $sen (1) - cos (1)$. Calcule os erros cometidos nos itens anteriores, isto é, a diferença em módulo entre
valor exato e o valor calculado (para isto, aproxime o valor exato para $0.301169$).



2. Use a regra de Simpson para estimar o valor da seguinte integral:

$$\int_0^1 (1 - x^2)^{3/2}\ dx.$$



3. Use a regra do trapézio para estimar a seguinte integral:

$$\int_0^1 xe^{-x^2}\ dx.$$



4. Usando $n=5$, calcule as seguintes integrais pela regra composta dos trapézios:


a)  $\int_1^2 x\ ln (x)\ dx$;

b)  $\int_0^1 x e^{-x}\ dx$.


5. Usando $n=5$, calcule as seguintes integrais pela regra composta de Simpson:


a)  $\int_0^1 x\ cos(x)\ dx$;

b)  $\int_0^1 (1 + x^2)^{3/2} \ dx$.


6. Considere a seguinte integral: $$\int_0^{1.5} e^x cos\ x\ dx.$$ Estime o quão grande deve ser $n$ na regra composta de Simpson para que a aproximação contenha 8 casas decimais corretas.

**Dica:** lembre-se que $h = (b-a)/(2n)$. Além disso, lembre-se que uma cota superior (estimativa) para o erro cometido por este método foi calculada em aula.

7. Usando $n=3$, calcule a seguinte integral pela regra de Gauss-Legendre:

$$\int_1^3 \frac{(sen (x))^2}{x}\ dx.$$

**Dica:** será necessário realizar uma mudança de variáveis para reescrever essa integral em um formato adequado para o uso dessa técnica de integração numérica.

# Gabarito 


Exercício 1: 

a)  $\approx 0.221634$

b)  $\approx 0.389928$

c)  $\approx 0.298859$

d)  $\begin{matrix}
    erro_a \approx 0.079535\\
    erro_b \approx 0.088758\\
    erro_c \approx 0.002310 \end{matrix}$

Exercício 2:

  $\approx 0.599679$



Exercício 3:

$\approx 0.183939$



Exercício 4: 

a)  $\approx 0.638603$

b)  $\approx 0.260912$

Exercício 5: 

a)  $\approx 0.381774$

b)  $\approx 1.567954$

Exercício 6:

Considere $f(x) = e^x cos(x)$ e calcule $f^{(4)}$. Perceba que
$M = \max_{x \in [0, 1.5]} |f^{(4)} (x)| \leq 4 \cdot e^{1.5}$. Majore a
estimativa para o erro dada em sala por $0.5 \times 10^{-8}$ para obter
que $55.44965895384878 \leq n$. Por fim, arredonde para cima, obtendo
$n \geq 56$. Você também pode encontrar uma estimativa um pouco menor,
de 46.37799514180625, se calcular $M$ exatamente.


Exercício 7:

$\approx 7.9482833 \times 10^{-1}$.



