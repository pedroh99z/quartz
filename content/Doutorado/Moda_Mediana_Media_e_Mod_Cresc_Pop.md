---
title: Moda, Mediana, Média e Modelos de Crescimento Populacional - Reunião do PIBIC-Jr
---
**Contexto:** Durante o meu doutorado, eu fui coorientador de um projeto do PIBIC-Jr. Em uma das reuniões, eu precisava ensinar os alunos a utilizar as planilhas do Excel (ou Google), e achei que seria importante também fazer uma revisão de alguns conceitos de estatística. Apesar do foco nas planilhas, acredito que as explicações que estão aqui podem ser úteis para quem estiver tentando aprender sobre o assunto, e por isso decidi publicar aqui. 
# Média, Mediana e Moda

A seguir, vamos ver algumas formas de determinar o "centro" de um
conjunto de dados. Mais especificamente, vamos falar sobre a Média
Aritmética, a Mediana e a Moda.

## Média (Aritmética)

A média aritmética é recomendada para conjuntos de dados simétricos,
isto é, um conjunto de dados onde não existem valores muito discrepantes
em relação ao conjunto todo. Se considerarmos o conjunto de $n$ valores
formado por $x_1, x_2, \dots, x_n$, a fórmula da média é dada por:
$$\overline{\chi} = \dfrac{x_1 + x_2 + \cdots + x_n}{n},$$ No Excel,
vimos que o comando para calcular a média é `MÉDIA(Val1; Val2; ...)`.

Contudo, é importante destacar que se tivermos um conjunto de dados
muito assimétrico, o recomendado é se utilizar a Moda ou a Mediana.

## Mediana

Nos casos em que o conjunto de dados é assimétrico, uma das possíveis
estratégias para encontrar um valor central é calcular a mediana, pois
ela não é afetada por valores extremos.

A mediana tem como característica que 50% dos elementos do conjunto
apresentam valores iguais ou maiores do que este valor, enquanto que os
50% restantes apresentam valores menores que a mediana.

Um jeito simples de calcular a mediana consiste em escrever os elementos
de um conjunto em ordem crescente. Se tivermos um conjunto de dados com
um número ímpar de elementos, a mediana é o valor que aparece no meio.

**Exemplo:** considere o conjunto $\{1, 3, 3, 6, 7, 8, 9\}$. Neste caso,
a mediana é 6.

Agora, se o conjunto de dados tiver um número par de elementos, a
mediana é a média aritmética dos dois termos que aparecem no meio.

**Exemplo:** considere o conjunto $\{3, 5, 7, 9\}$. Neste caso, a
mediana é $$\dfrac{5+7}{2} = 6.$$

No Excel, podemos calcular a moda com o seguinte comando:
`MED(Val1; Val2; ...)`

## Moda

A moda também é uma estratégia para se trabalhar com conjuntos de dados
assimétricos. Ela consiste em tomar o valor que mais se repete em um
conjunto de dados, ou seja, a moda se trata do valor mais frequente.

Uma das vantagens da moda é que podemos usá-la para calcular elementos
centrais em conjuntos que não são numéricos.

**Exemplo:** considere o conjunto
$$\{\text{maçã}, \text{banana}, \text{laranja}, \text{laranja}, \text{laranja}, \text{pêssego}\}.$$
O elemento que mais se repete é a palavra *laranja*, e portanto a moda
desse conjunto de dados é laranja.

No Excel, podemos calcular a moda com o seguinte comando:
`MODO(Val1; Val2; ...)`

Fonte:
<https://periodicoseletronicos.ufma.br/index.php/cadernosdepesquisa/article/view/9328/5543>

<https://pt.wikipedia.org/wiki/Mediana_(estat%C3%ADstica)>

<https://pt.wikipedia.org/wiki/Moda_(estat%C3%ADstica)>

# Estimar Crescimento Populacional

Existem diversas estratégias para estimar o crescimento populacional ao
longo do tempo. Dentre os modelos matemáticos mais famosos com esta
finalidade, temos os modelos de **Malthus** e **Verhulst**. Em ambos os
modelos, considera-se uma informação inicial sobre a população, isto é,
**o número de indivíduos inicial ($P_0$)** que se usará como base para
as estimativas. Além disso, considera-se uma taxa de crescimento da
população ($r$). Para o modelo de Verhulst, considera-se também uma
capacidade populacional máxima $M$.

A partir de agora, vamos utilizar a letra $P$ para nos referirmos ao
número de indivíduos, e $t$ para o tempo em anos. Desta forma, vamos
escrever $P(t)$ para nos referirmos ao número de indivíduos após $t$
anos.

## Malthus

A fórmula que descreve o modelo de crescimento populacional dado por
Malthus é: $$P(t) = P_0 \cdot e^{r \cdot t},$$ onde $e$ corresponde ao
número de Euler (aproximadamente 2,71). Este modelo é também conhecido
como modelo exponencial, ou modelo Malthusiano.

## Verhulst

A fórmula que descreve o modelo de Verhulst é:
$$P(t) = \dfrac{P_0 \cdot e^{r \cdot t}}{1 + \dfrac{P_0 \cdot ( e^{r \cdot t} - 1 ) }{M}}.$$

Fonte: <https://rce.casadasciencias.org/rceapp/pdf/2018/041/>
