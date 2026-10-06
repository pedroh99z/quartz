---
title: Divisões Proporcionais e Regra de Três
tags: [divisões proporcionais, regra de três, matemática básica]
draft: false
---

**Recomendação:** veja também a [aula anterior](./proporcoes.md).

# Divisões Proporcionais

Escolha um número $n$. Podemos decompor $n$ como a soma de três números
$a, b$ e $c$, isto é, escrever $n = a + b + c$. Imagine que nós queremos
decompor $n$ em três partes seguindo uma determinada [proporção](./proporcoes.md). Esta
proporção pode ser direta ou indireta, como vimos anteriormente. Vamos
estudar estes dois casos em exemplos:\
Exemplo 1: Vamos decompor o número 180 em 3 partes proporcionais a 3, 4
e 11 de modo que esta proporção seja direta. Neste caso, queremos
escrever $180 = a + b + c$, de modo que tenhamos $a, b$ e $c$
diretamente proporcionais à 3, 4 e 11. Como vimos anteriormente, isto é
o mesmo que dizer que

$$
\frac{a}{3} = \frac{b}{4} = \frac{c}{11} = k,
$$
para alguma constante $k$.

Em outras palavras, temos que $a = 3k$, $b = 4k$ e $c = 11k$. Uma vez
que $a + b + c = 180$, temos que

$$
3k + 4k + 11k = 180 \Leftrightarrow 18k = 180 \Leftrightarrow k = 10.
$$

Voltando aos valores $a,\ b$ e $c$ e substituindo o valor $k$
encontrado, temos que $a = 30$, $b = 40$ e $c = 110$. Portanto, podemos
decompor 180 da seguinte forma:

$$
180 = 30 + 40 + 110.
$$

Exemplo 2: Vamos decompor o número 341 em partes inversamente
proporcionais a 2, 3 e 5. Em outras palavras, queremos escrever
$341 = a + b + c$, onde $a,\ b$ e $c$ respeitam as seguintes equações

$$
2 \cdot a = 3 \cdot b = 5 \cdot c = k,
$$

onde $k$ é uma constante. A
partir daqui, o procedimento para encontrar $a,\ b$ e $c$ é bem parecido
com o que foi feito no exemplo anterior. Temos que

$$
a = \frac{k}{2},\ b = \frac{k}{3}\ \text{e}\ c = \frac{k}{5}.
$$

Como $a + b + c = 341$, segue que
$\frac{k}{2} + \frac{k}{3} + \frac{k}{5} = 341$, ou equivalentemente,

$$
\frac{15k + 10k + 6k}{30} = 341 \Leftrightarrow \frac{31k}{30} = 341 \Leftrightarrow k = \frac{341 \cdot 30}{31} = 330.
$$

Substituindo o $k$ encontrado em $a,\ b$ e $c$, temos que $a = 165$,
$b = 110$ e $c = 66$. Neste caso, podemos decompor $341$ da seguinte
forma:

$$
341 = 165 + 110 + 66.
$$

# Regra de Três Simples

A regra de três simples é uma técnica para resolver problemas envolvendo
quatro valores, onde nós conhecemos 3 deles e existe uma certa proporção
entre os termos. Por exemplo, suponha que um sachê de suco deva ser
misturado em meio litro de água para que fique bem concentrado (nem
muito doce, nem muito aguado). Se precisarmos preparar 3 litros de suco
utilizando esses sachês, quantos sachês devemos comprar?

Problemas como esse podem ser resolvidos utilizando a regra de três.
Seja $x$ o número de sachês que precisamos comprar. Se lembrarmos das
aulas de proporção, percebemos que 1 sache está para 0.5 litros de água
assim como x sachês estão para 3 litros de água. Em outras palavras,

$$
\frac{1}{0.5} = \frac{x}{3}.
$$

Neste caso, podemos isolar $x$ e descobrir que seu valor é $6$. A regra
de três nos dá um processo mais prático de descobrir que $x = 6$. Veja:

$$
\begin{matrix}
\text{1} & \text{sachê} & \text{-------} & \text{0.5} & \text{litros}\\
\text{x} & \text{sachês} & \text{-------} & \text{3} & \text{litros}
\end{matrix}
$$

A regra de três simples nos diz que podemos "multiplicar cruzado" os
valores acima, obtendo

$$
1 \cdot 3 = 0.5 \cdot x \Leftrightarrow 1 \cdot 3 = \frac{x}{2} \Leftrightarrow x = 3 \cdot 2 = 6.
$$

Portanto, seriam necessários 6 sachês para preparar 3 litros de suco.

O exemplo do suco dado acima representa problemas nos quais os termos
envolvidos são diretamente proporcionais. Temos também problemas onde as
grandezas envolvidas podem ser inversamente proporcionais. Considere o
seguinte problema: um carro com velocidade média de 80 km/h percorre uma
determinada distância em um tempo de 5 horas. Em quanto tempo este carro
percorreria o mesmo caminho se sua velocidade média fosse 100 km/h?

Perceba que se a velocidade do carro aumenta, o tempo que ele gasta para
percorrer seu caminho diminui. Logo, a velocidade média do carro e o
tempo gasto são inversamente proporcionais, isto é, quando um aumenta, o
outro diminui. Neste caso, a regra de três sofre uma leve alteração:

$$
\begin{matrix}
\text{80} & \text{km/h} & \text{-------} & \text{5} & \text{horas}\\
\text{100} & \text{km/h} & \text{-------} & \text{x} & \text{horas}
\end{matrix}
$$

Ao invés de fazermos uma multiplicação cruzada, devemos
escrever a seguinte proporção:

$$
\frac{80}{100} = \frac{x}{5},
$$

ou, se preferir, a seguinte
proporção:

$$
\frac{100}{80} = \frac{5}{x}.
$$ 

O importante aqui é perceber que na
parte de cima das frações vai sempre o menor número (no primeiro caso),
ou sempre o maior número (no segundo caso). Depois, podemos multiplicar
cruzado, e isolar $x$, obtendo $x = 4$ horas.

**Dica:** sempre que você for resolver exercícios envolvendo a regra de
três, você deve primeiro saber se as grandezas envolvidas são
diretamente proporcionais ou inversamente proporcionais. Se você não
souber isso, corre o risco de usar a regra de três de forma errada.

# Exercícios

1.  (PUC) Dois amigos jogaram R\$360,00 na loteria esportiva, sendo que
    o primeiro entrou com R\$140,00 e o segundo R\$220,00. Ganharam um
    prêmio de R\$162.000,00. Como deve ser rateado o prêmio?

    a\) R\$63.000,00 e R\$99.000,00.\
    b) R\$70.000,00 e R\$92.000,00.\
    c) R\$62.000,00 e R\$100.000,00.\
    d) R\$50.000,00 e R\$112.000,00.\
    e) R\$54.000,00 e R\$108.000,00.

2.  (NCE) Antônio, Bernardo, Cláudio e Daniel elaboraram juntos uma
    prova de 40 questões, tendo recebido por ela um total de
    R\$2.200,00. Os três primeiros fizeram o mesmo número de questões e
    Daniel fez o dobro do que fez cada um dos outros. Se o dinheiro deve
    ser repartido proporcionalmente ao trabalho de cada um, Daniel
    deverá receber uma quantia, em reais, igual a:

    a\) 800,00.\
    b) 820,00.\
    c) 850,00.\
    d) 880,00.\
    e) 890,00.

3.  (UFBA) Um carro consumiu 50 litros de álcool para percorrer 600 km.
    Supondo condições equivalentes, esse mesmo carro, para percorrer 840
    km, consumirá:

    a\) 68 litros.\
    b) 75 litros.\
    c) 70 litros.\
    d) 80 litros.\
    e) 85 litros.

4.  (Vunesp) Uma pessoa digitou um trabalho em sete dias, trabalhando
    oito horas por dia. Para realizar o mesmo trabalho, nas mesmas
    condições, só que trabalhando apenas quatro horas por dia, ela
    demoraria:

    a\) 8 dias.\
    b) 9 dias.\
    c) 10 dias.\
    d) 11 dias.\
    e) 14 dias.

Gabarito:\
1 - A\
2 - D\
3 - C\
4 - E
