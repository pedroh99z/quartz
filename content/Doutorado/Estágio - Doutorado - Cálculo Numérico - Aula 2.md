
# ⚠️ AVISO

Esta aula foi elaborada como parte do meu primeiro estágio de docência do doutorado. Originalmente, este texto foi escrito em *latex*, na forma de apresentação *beamer*. A versão que estou apresentando aqui foi convertida automaticamente de latex para *markdown* pelo programa *pandoc*, e pode conter erros de formatação.

### Derivada de uma Função

Lembremos de Cálculo 1 que dada uma função
$f : \mathbb{R}\to \mathbb{R}$, a derivada de $f$ foi definida como
$$f'(x) = \lim_{h \to 0} \dfrac{f(x+h) - f(x)}{h}.$$



### Diferenças Finitas

Considere a expansão em série de Taylor de $f$ em torno de um ponto $x$:
$$f(x+h) = f(x) + f'(x)h + \dfrac{1}{2} f''(x) h^2 + \dfrac{1}{3!} f'''(x) h^3 + \cdots$$
Podemos truncar a série, desconsiderando os termos de ordem 2 e
superior, obtendo a seguinte aproximação:
$$f(x+h) \approx f(x) + f'(x)h$$ Ou equivalentemente,
$$f'(x) \approx \dfrac{f(x+h) - f(x)}{h}.$$ A aproximação acima é
chamada **diferença finita progressiva** de ordem 1.



Outra forma de aproximação é a chamada **diferença finita central**.
Podemos considerar as duas expansões a seguir:
$$f(x+h) = f(x) + f'(x)h + \dfrac{1}{2} f''(x) h^2 + \dfrac{1}{3!} f'''(x) h^3 + \cdots$$
e
$$f(x-h) = f(x) - f'(x)h + \dfrac{1}{2} f''(x) h^2 - \dfrac{1}{3!} f'''(x) h^3 + \cdots$$
Truncando ambas as expansões após o terceiro termo, e depois subtraindo
a segunda na primeira, temos que $$f(x+h) - f(x - h) \approx 2 f'(x) h$$
$$\Leftrightarrow f'(x) \approx \dfrac{f(x+h) - f(x - h)}{2h}$$ Observe
que ao truncar a partir do terceiro termo, esta aproximação tem ordem 2.



Da expansão de Taylor com sinal negativo também podemos obter a seguinte
aproximação: $$f'(x) \approx \dfrac{f(x) - f(x-h)}{h},$$ chamada de
**diferença finita regressiva** de ordem 1.



Podemos também aproximar as derivadas de segunda ordem. Considere
novamente as expansões
$$f(x+h) = f(x) + f'(x)h + \dfrac{1}{2} f''(x) h^2 + \dfrac{1}{3!} f'''(x) h^3 + \cdots$$
e
$$f(x-h) = f(x) - f'(x)h + \dfrac{1}{2} f''(x) h^2 - \dfrac{1}{3!} f'''(x) h^3 + \cdots$$
Truncando ambas as expansões após o terceiro termo, podemos somar ambas
as equações, obtendo $$f(x+h) + f(x - h) \approx 2 f(x) + f''(x)h^2$$
$$\Leftrightarrow f''(x) \approx \dfrac{f(x+h) - 2 f(x) + f(x - h)}{h^2}.$$



### Fórmulas de Diferenças Finitas

É possível obter as fórmulas de diferenças finitas de outra maneira.
Dados os pontos $x_1, x_2, \dots, x_n$, podemos obter uma aproximação
para $f'$ em um ponto $x^*$ da seguinte forma:
$$f'(x^*) \approx c_1 f(x_1) + c_2 f(x_2) + \dots + c_n f(x_n),$$ onde
esta aproximação é exata para polinômios de grau até $n-1$.



Supondo $f(x) = 1$, temos
$$0 = (1)'     = f'(x^*) = c_1 + c_2 + \dots + c_n.$$ Supondo
$f(x) = x^k$, com $k = 1, 2, \dots, n-1$ e procedendo de forma análoga,
temos $$\begin{matrix}
1 & = & (x)' |_{x = x^*} & = & c_1 x_1 + \cdots + c_n x_n\\\\
2x^* & = & (x^2)' |_{x = x^*} & = & c_1 x_1^2 + \cdots + c_n x_n^2\\
&\vdots &&\vdots&\\
(n-1)(x^*)^{n-2} & = & (x^{n-1})' |_{x = x^*} & = & c_1 x_1^{n-1} + \cdots + c_n x_n^{n-1}\\
\end{matrix}$$



Podemos escrever as equações obtidas anteriormente no formato de um sistema:

$$
\begin{bmatrix}
1 & 1 & \cdots & 1\\
x_1 & x_2 & \cdots & x_n\\
x_1^2 & x_2^2 & \cdots & x_n^2\\
\vdots & \vdots & \ddots & \vdots\\
x_1^{n-1} & x_2^{n-1} & \cdots & x_n^{n-1}\\
\end{bmatrix}
\begin{bmatrix}
c_1\\
c_2\\
c_3\\
\vdots \\
c_n
\end{bmatrix}
=
\begin{bmatrix}
0\\
1\\
2x^*\\
\vdots\\
(n-1)(x^*)^{n-2}
\end{bmatrix}.
$$

Resolvendo o sistema acima, temos as constantes $c_1, c_2, \dots, c_n$
necessárias para aproximar $f'$ pela expressão
$$f'(x^*) \approx c_1 f(x_1) + c_2 f(x_2) + \dots + c_n f(x_n).$$

Pela construção realizada anteriormente, se $f$ for um polinômio de até
grau $n-1$, esta aproximação será exata.




### Exemplo

Considere $x_1 = -h,\ x_2 = 0$ e $x_3 = h$, e faça $x^* = x_2 = 0$.
Obtenha uma fórmula para aproximar $f'(x^*)$.


Basta resolver o seguinte sistema:

$$
\begin{bmatrix}
1 & 1 & 1\\
-h & 0 & h\\
h^2 & 0 & h^2 \end{bmatrix} \begin{bmatrix}
c_1\\
c_2\\
c_3 \end{bmatrix} = \begin{bmatrix}
0\\
1\\
0 \end{bmatrix}.
$$
Resolvendo o sistema acima, temos
$c_1 = - \frac{1}{2h}$, $c_2 = 0$ e $c_3 = \frac{1}{2h}$. Assim sendo,

$$f'(x^*) \approx c_1 f(x_1) + c_2 f(x_2) + c_3 f(x_3)$$
$$= - \dfrac{1}{2h} f(x_1) + \dfrac{1}{2h} f(x_3)$$
$$= \dfrac{f(x_3) - f(x_1)}{2h}.$$



### Derivada via Ajuste ou Interpolação

Alternativamente, podemos considerar os pares $(x_i, f(x_i))$, com
$i = 1, 2, \dots, n$, e construir uma curva que ajusta ou interpola
estes pontos. Depois, podemos utilizar a expressão desta curva para
calcular sua derivada, obtendo assim uma aproximação para $f'$.




**Exemplo**

Considere a seguinte tabela:

    $x$     0   1   2   3
  -------- --- --- --- ---
   $f(x)$   1   2   5   9

Supondo que $f$ é derivável, aproxime $f'$ nos mesmos pontos.


A parábola que melhor ajusta estes pontos é
$$Q(x) = 0.95 + 0.45x + 0.75x^2.$$ Fazendo $f(x) \approx Q(x)$, temos
que $$f'(x) \approx Q'(x) = 0.45 + 1.5x.$$ Neste caso,

     $x$           0                1                2                3
  --------- ---------------- ---------------- ---------------- ----------------
   $f'(x)$   $\approx 0.45$   $\approx 1.95$   $\approx 3.45$   $\approx 4.95$



### Diferenças Finitas Avançadas 

O Método das Diferenças Finitas
convencional não é infalível. Geralmente, quando desejamos obter
aproximações melhores, reduzimos o valor de $h$. No entanto, tomar $h$
muito pequeno em implementações computacionais pode gerar erros de
arredondamento.


**Exemplo** Calcule a derivada de $f(x) = x^2$ em $x=2$ pelo método das
diferenças finitas progressivas de ordem 1, tomando $h = 10^{-100}$.


Observe que será retornado $f'(x) = 0$ ao realizar este cálculo
utilizando nossa implementação.



### Porque isso acontece?

Isso acontece, pois como $h$ é muito pequeno, o computador acabou
arredondando $f(2+h)$ e $f(2)$ para o mesmo valor. Consequentemente,
$$f'(2) = \dfrac{f(2 + h) - f(2)}{h} = \dfrac{0}{h} = 0.$$

Erros assim são bastante comuns ao utilizarmos os métodos de diferenças
finitas. Um valor de $h$ considerado mais seguro a ser utilizado é
$h = 10^{-8}$, embora esta escolha também não seja infalível.



No intuito de evitar esses erros de cancelamento, foi desenvolvida uma
nova técnica na qual não há mais a necessidade de se realizar esta
subtração. Esta técnica ficou conhecida como **Aproximação do Passo
Complexo**, em um paper escrito por William Squire e George Trapp. A
estratégia consiste em realizar a seguinte aproximação:
$$f'(x) \approx Im \left( \frac{f(x+ih)}{h}\right),$$ onde $Im (z)$
denota a parte imaginária de $z$.

Esta aproximação ainda sofre com erros de arredondamento, embora não
prejudique tanto a precisão da aproximação como nas diferenças finitas.


**Observação** Para que esta técnica funcione, é necessário que $f$ seja uma
função real, isto é, não podem existir números imaginários em sua
expressão.





**Exemplo** Calcule a derivada de $f(x) = x^2$ em $x=2$ pela Aproximação do
Passo Complexo, tomando $h = 10^{-100}$.



**Exemplo** Calcule a derivada de $f(x) = e^{x^2} sen(1/x)$ em $x=1.3$ pela
Aproximação do Passo Complexo, tomando $h = 10^{-100}$.



**Exemplo** Calcule a derivada de $f(x) = log(1/x)$ em $x=7$ pela
Aproximação do Passo Complexo, tomando $h = 10^{-100}$.





### Equações Diferenciais Ordinárias (EDO)


**Definição** Uma equação diferencial ordinária (EDO) de ordem $n$ pode ser
expressa na forma:
$$F\left(x, y(x), \dfrac{dy}{dx}(x), \dfrac{d^2y}{d^2x}(x), \dots, \dfrac{d^ny}{d^nx}(x)\right) = 0,$$
onde $y$ é uma função que depende de $x$.


Alguns exemplos:

-   $y' + y = 0$;

-   $\dfrac{d}{dt} N(t) = c N(t) \Leftrightarrow \dfrac{d}{dt} N(t) - c N(t) = 0$;

-   $m \dfrac{d^2}{d^2t} x(t) = - k (t) x(t) \Leftrightarrow m \dfrac{d^2}{d^2t} x(t) + k (t) x(t) = 0$.



### Problema de Valor Inicial (PVI) de 1ª Ordem


**Definição** Um problema de valor inicial (PVI) de 1ª ordem é definido
como: $$\left\{\begin{matrix}
\frac{dy}{dx}(x) &=& f(x, y(x))\\
y(x_0) &=& y_0,
\end{matrix}\right.$$ onde
$f : \Omega \subset \mathbb{R}^2 \to \mathbb{R}$,
$\Omega = \{ (x,\ y)\ |\ a \leq x \leq b \text{ e } -\infty < y < + \infty \}$,
com $y : [a, b] \to \mathbb{R}$.




### Solução Numérica para EDO's de Primeira Ordem

Os passos para encontrar a
solução numérica para o (PVI) são os seguintes:

-   Dividimos o intervalo $[a,b]$ em $n$ subintervalos $[x_i, x_{i+1}]$,
    com $i = 0, 1, \dots, n$. Para pontos igualmente espaçados, podemos
    escrever $h = (b-a)/n$, e $x_i = x_0 + i h$;

-   Aproximamos $y$ nos pontos $x_i$, para $i=1, 2, \dots, n$. Com isso,
    obtemos os seguintes pontos:

         $i$       $x_i$      $y(x_i)$
      ---------- ---------- ------------
         $0$       $x_0$      $y(x_0)$
         $1$       $x_1$      $y(x_1)$
       $\vdots$   $\vdots$    $\vdots$
         $n$      $x_{n}$    $y(x_{n})$

Esses pontos podem ser usados para interpolar $y$.



### Expansão de $y$ em Série de Taylor 

Supondo que a função $f$ no PVI seja
suficientemente diferenciável, podemos expandir $y$ em série de Taylor
em torno de $x_0$ da seguinte forma:
$$y(x_0 + h) = y(x_0) + y'(x_0) h + \dfrac{1}{2} y''(x_0) h^2 + \dfrac{1}{3!} y'''(x_0) h^3 + \cdots$$
Como $y' = f$, temos que
$$y'' = f',\ y''' = f'',\ \dots, y^{(n)} = f^{(n-1)}, \dots$$
Substituindo na expansão de Taylor, temos que
$$y(x_0 + h) = y(x_0) + f(x_0, y(x_0)) h + \dfrac{1}{2} f'(x_0, y(x_0)) h^2 + \dfrac{1}{3!} f''(x_0, y(x_0)) h^3 + \cdots$$



Para obter uma aproximação de $y$ em $x_0 + h$ de ordem $k$, podemos
truncar a expansão de Taylor, desconsiderando todos os termos após o
termo de ordem $k$. Por exemplo, para uma aproximação de ordem 3:
$$y(x_0 + h) \approx y(x_0) + f(x_0, y(x_0)) h + \dfrac{1}{2} f'(x_0, y(x_0)) h^2 + \dfrac{1}{3!} f''(x_0, y(x_0)) h^3.$$
Neste caso, bastaria calcular as derivadas de $f$ e depois substituir na
expressão acima para obter a aproximação de $y$ em $x_0 + h$.




**Exemplo** Utilizando Taylor até terceira ordem, calcule a solução do PVI

$$
\left\{ \begin{matrix}
y' &=& 1 - x^{-1} y\\
y(2) &=& 2
\end{matrix} \right.
$$
em $x = 2.1$.


Considere $f(x, y(x)) = 1 - x^{-1} y$. Temos que
$$f'(x, y(x)) = x^{-2}y - x^{-1}y'$$ $$= x^{-2}y - x^{-1} f(x, y(x))$$ e
$$f''(x, y(x)) = -2x^{-3} y + x^{-2} y' + x^{-2} y' - x^{-1} y''$$
$$= -2x^{-3} y + 2 x^{-2} f(x, y(x)) - x^{-1} f'(x, y(x)).$$



Como $y(2) = 2$, segue que $f(2, 2) = 0$, e então $f'(2, 2) = 0.5$, e
finalmente, $f''(2, 2) = -0.75$. Substituindo na expansão de Taylor
truncada até o termo de ordem $3$, temos que
$$y(2.1) \approx y(2) + f(2, 2) 0.1 + \dfrac{1}{2} f'(2, 2) 0.1^2 + \dfrac{1}{3!} f''(2, 2) 0.1^3.$$
$$
= 2 + 0 \cdot 0.1 + \dfrac{1}{2} 0.5 \cdot 0.1^2 + \dfrac{1}{3!} (-0.75) \cdot 0.1^3.
$$

$$
%\approx 2.002375
= 2.002375
$$




### Método de Euler 

Considere novamente a expansão de Taylor de $y$ em
$x_0$:
$$y(x_0 + h) = y(x_0) + f(x_0, y(x_0)) h + \dfrac{1}{2} f'(x_0, y(x_0)) h^2 + \dfrac{1}{3!} f''(x_0, y(x_0)) h^3 + \cdots$$
Vamos truncar a expansão após o termo de primeira ordem:
$$y(x_0 + h) \approx y(x_0) + f(x_0, y(x_0)) h.$$ Vamos dividir $[a, b]$
em $n$ subintervalos de tamanho $h = (b-a)/n$. Então, $x_i = x_0 + i h$.
Procedendo de forma análoga para cada um desses intervalos, temos que
$$y(x_{i+1}) = y(x_i) + h f(x_i, y(x_i)), i = 0, 1, \dots, n-1.$$




**Exemplo** Considere o seguinte PVI: $$\left\{\begin{matrix}
y' = 2 y\\
y(0) = 1
\end{matrix}\right.$$ Calcule $y(1)$ pelo método de Euler, com
$h = 0.2$.


Considere $f(x, y(x)) = 2y$. Então, para $x_0 = 0$,


$y(x_0) = y(0) = 1;$\
$y(x_1) = y(0.2) \approx y(x_0) + 0.2 f(x_0, y(x_0)) = 1 + 0.2 \cdot 2 = 1.4;$\
$y(x_2) = y(0.4) \approx y(x_1) + 0.2 f(x_1, y(x_1)) = 1.4 + 0.2 \cdot 2.8 = 1.96;$\
$y(x_3) = y(0.6) \approx y(x_2) + 0.2 f(x_2, y(x_2)) = 1.96 + 0.2 \cdot 3.92 \approx 2.744;$\
$y(x_4) = y(0.8) \approx y(x_3) + 0.2 f(x_3, y(x_3)) = 2.744 + 0.2 \cdot 5.488 = 3.8416;$\
$y(x_5) = y(1) \approx y(x_4) + 0.2 f(x_4, y(x_4)) = 3.8416 + 0.2 \cdot 7.6832 = 5.37824.$




### Método de Euler Modificado 

Considere novamente a expansão de Taylor de
$y$ em $x_0$:
$$y(x_0 + h) = y(x_0) + y'(x_0) h + \dfrac{1}{2} y''(x_0) h^2 + \dfrac{1}{3!} y'''(x_0) h^3 + \cdots$$
Dessa vez, vamos truncar após o termo de grau 2, obtendo
$$y(x_0 + h) \approx y(x_0) + y'(x_0) h + \dfrac{1}{2} y''(x_0) h^2.$$
Agora, vamos aproximar $y''(x_0)$ utilizando diferenças finitas:
$$y''(x_0) \approx \dfrac{y'(x_0+h) - y'(x_0)}{h}.$$



Substituindo na expansão de Taylor truncada, temos
$$y(x_0 + h) \approx y(x_0) + y'(x_0) h + \dfrac{h}{2} [y'(x_0+h) - y'(x_0)].$$
Como $y' = f$, temos que
$$y(x_0 + h) \approx y(x_0) + f(x_0, y(x_0)) h + \dfrac{h}{2}[ f(x_0 + h, y(x_0 + h)) - f(x_0)],$$
ou equivalentemente,
$$y(x_1) \approx y(x_0) + f(x_0, y(x_0)) h + \dfrac{h}{2} [f(x_1, y(x_1)) - f(x_0)],$$
onde $x_1 = x_0 + h$. Note que para aproximar $y(x_1)$ pela equação
acima, precisamos do valor de $y(x_1)$, o que a princípio pode não fazer
sentido.



Para contornar este problema, realizamos uma aproximação de primeira
ordem para $y(x_1)$:

$$y(x_1) \approx y(x_0) + h y'(x_0) = y(x_0) + h f(x_0, y(x_0)).$$ Neste
caso,
$$y(x_1) \approx y(x_0) + f(x_0, y(x_0)) h + \dfrac{h}{2} [f(x_1, \overline{y}(x_1)) - f(x_0)],$$
onde $\overline{y}(x_1) = y(x_0) + h f(x_0, y(x_0))$.



Sendo assim, no **Método de Euler Modificado**, temos
$$y(x_{i+1}) \approx y(x_i) + f(x_i, y(x_i)) h + \dfrac{h}{2} [f(x_{i+1}, \overline{y}(x_{i+1})) - f(x_0)],$$
$i = 0, 1, \dots, n-1,$ onde
$$\overline{y}(x_{i+1}) = y(x_i) + h f(x_i, y(x_i)).$$



Método de Runge-Kutta Por conveniência, vamos denotar $y_i = y(x_i)$. Os
métodos de Runge-Kutta tem um algoritmo da forma:
$$y_{i+1} = y_i + h \sum_{j=1}^m w_j k_j,$$ onde

-   $m$ é a ordem do método;

-   Cada $k_j$, $j = 1, \dots, m$, é a $f$ calculada em um determinado
    ponto $(x, y)$, onde $x \in [x_i, x_{i+1}]$;

-   Cada $w_j$, $j = 1, \dots, m$, são constantes tais que
    $\sum_{j=1}^m w_j = 1$;

-   $\sum_{j=1}^m w_j k_j$ é a média ponderada de coeficientes angulares
    sobre os intervalos $[x_i, x_{i+1}]$.



Quando $m = 1$, $w_1 = 1$ e $k_1 = f(x_i, y_i)$, temos
$$y_{i+1} = y_i + h f (x_i, y_i),$$ ou seja, o Método de Runge-Kutta
coincide com o Método de Euler.



### Método de Runge-Kutta de 2ª Ordem 

No caso em que $m = 2$ e
$w_1 = w_2 = \frac{1}{2}$, temos $$\left\{\begin{matrix}
y_{i+1} = y_i + \dfrac{h}{2} [ k_1 + k_2 ],\ i \geq 0\\
k_1 = f(x_i, y_i)\\
k_2 = f(x_i + h, y_i + h k_1)
\end{matrix}\right.$$ Neste caso, o Método de Runge-Kutta coincide com o
Método de Euler Modificado.



### Método de Runge-Kutta de 3ª Ordem 

Fazendo $m = 3$,
$w_1 = w_3 = \frac{1}{6}$ e $w_2 = \frac{4}{6}$, temos

$$
\left\{ \begin{matrix}
y_{i+1} & = & y_i + \dfrac{h}{6}[k_1 + 4 k_2 + k_3],\ i \geq 0\\
k_1 & = & f(x_i, y_i)\\
k_2 & = & f(x_i + \frac{1}{2} h, y_i + \frac{1}{2} h k_1)\\
k_3 & = & f(x_i + h, y_i + 2 h k_2 - h k_1)
\end{matrix} \right.
$$




### Método de Runge-Kutta de 4ª Ordem 

Fazendo $m = 4$,
$w_1 = w_4 = \frac{1}{6}$ e $w_2 = w_3 = \frac{2}{6}$, temos

$$
\left\{ \begin{matrix}
y_{i+1} & = & y_i + \dfrac{h}{6}[k_1 + 2 k_2 + 2 k_3 + k_4],\ i \geq 0\\
k_1 & = & f(x_i, y_i)\\
k_2 & = & f(x_i + \frac{1}{2} h, y_i + \frac{1}{2} h k_1)\\
k_3 & = & f(x_i + \frac{1}{2} h, y_i + \frac{1}{2} h k_2)\\
k_4 & = & f(x_i + h, y_i + h k_3)
\end{matrix} \right.
$$





**Exemplo** Considere o seguinte PVI: $$\left\{ \begin{matrix}
y' = y + x\\
y(0) = 1
\end{matrix} \right.$$ Aproxime $y(1)$ pelo Método de Runge-Kutta de 4ª
Ordem, com $h = 1$.


Considere $f(x, y) = y + x$. Fazendo $x_0 = 0$, temos que


$k_1 = f(x_0, y_0) = f(0, y(0)) = f(0, 1) = 1;$\
$k_2 = f(x_0 + \frac{1}{2}, y_0 + \frac{1}{2} k_1) = f(0.5, 1.5) = 2;$\
$k_3 = f(x_0 + \frac{1}{2}, y_0 + \frac{1}{2} k_2) = f(0.5, 2) = 2.5;$\
$k_4 = f(x_0 + 1, y_0 + 1 \cdot k_3) = f(1, 2.5) = 4.5.$


Então,


$y(1) \approx y_{1} = 1 + \dfrac{1}{6}[1 + 2 \cdot 2 + 2 \cdot 2.5 + 4.5] \approx 3.4167.$




### Sistemas de Equações Diferenciais

Considere o seguinte sistema de $m$ EDO's de primeira ordem:

$$
\left\{ \begin{matrix}
y_1' & = & f_1 (x, y_1, \dots, y_m),\ y_1(x_0) = y_{0_1}\\
y_2' & = & f_2 (x, y_1, \dots, y_m),\ y_2(x_0) = y_{0_2}\\
& \vdots & \\
y_m' & = & f_n (x, y_1, \dots, y_m),\ y_n(x_0) = y_{0_m}\\
\end{matrix} \right.
$$
Podemos escrever este sistema de forma mais
simples do seguinte modo: $$\left\{ \begin{matrix}
Y' & = & F (x,Y)\\
Y(x_0) & = & Y_0
\end{matrix} \right.$$ onde $$\begin{matrix}
Y(x) = \begin{bmatrix}
y_1(x)\\
y_2(x)\\
\vdots \\
y_m(x)
\end{bmatrix},
&
F(x, Y) = \begin{bmatrix}
f_1(x, Y)\\
f_2(x, Y)\\
\vdots \\
f_m(x, Y)
\end{bmatrix},
&
Y_0 = \begin{bmatrix}
y_{0_1}\\
y_{0_2}\\
\vdots \\
y_{0_m}\\
\end{bmatrix}.
\end{matrix}$$



### Método de Euler para um Sistema de $m$ EDO's de Primeira Ordem

Aplicando o Método de Euler sobre este sistema mais simples, temos
$$Y_{i+1} = Y_i + h F(x_i, Y_i).$$ Para ilustrar, analisemos o caso
$m = 2$. Neste caso, temos o sistema $$\left\{ \begin{matrix}
y' & = & f (x,y, z)\\
z' & = & g (x,y, z)\\
y(x_0) & = & y_0\\
z(x_0) & = & z_0
\end{matrix} \right.$$ Aplicando o Método de Euler sobre este sistema,
obtemos as seguintes expressões: $$\begin{matrix}
y_{i+1} = y_i + h f(x_i, y_i, z_i)\\
z_{i+1} = z_i + h g(x_i, y_i, z_i)
\end{matrix}$$



Equações Diferenciais de Ordem Superior Considere o seguinte PVI com uma
EDO de ordem $m$: $$\left\{ \begin{matrix}
y^{(m)} & = & f(x, y, y', y'', \dots, y^{(m)}),\ n \geq 2\\
y(x_0) & = & y_0\\
y'(x_0) & = & y_0'\\
&\vdots&\\
y^{(m-1)}(x_0) & = & y^{(m-1)}_0
\end{matrix} \right.$$ Faça a seguinte mudança de variáveis:

$$
\begin{matrix}
y_1 = y', & y_2 = y_1', & y_3 = y_2', & \cdots, & y_{m-1} = y_{m-2}'.
\end{matrix}
$$




Fazendo essas mudanças, o PVI fica reescrito da seguinte forma:

$$
\left\{
\begin{matrix}
y' & = & y_1\\
y_1' & = & y_2\\
y_2' & = & y_3\\
&\vdots&\\
y_{m-2}' & = & y_{m-1}\\
y_{m-1}' & = & f(x, y, y_1, y_2, \dots, y_{m-1})\\
y(x_0) & = & y_0\\
y_1(x_0) & = & y_0'\\
&\vdots&\\
y_{m-1}(x_0) & = & y^{(m-1)}_0
\end{matrix}
\right.
$$




Para ilustrar, vamos considerar um PVI de segunda ordem ($m = 2$):

$$
\left\{
\begin{matrix}
y'' & = & f(x, y, y')\\
y(x_0) & = & y_0\\
y'(x_0) & = & y_0'
\end{matrix}
\right.
$$
Vamos fazer a seguinte mudança de variável: $$z = y'.$$ Neste
caso, temos que $z' = y''$, e portanto o sistema ficará reescrito da
seguinte forma: $$\left\{
\begin{matrix}
y' & = & z\\
z' & = & f(x, y, z)\\
y(x_0) & = & y_0\\
z(x_0) & = & y_0'
\end{matrix}
\right.$$ Note que o PVI reescrito dessa forma possui apenas EDO's de 1ª
ordem, logo podemos aplicar o Método de Euler para resolvê-lo.




### Exercício

2\) Considere o seguinte PVI: $$\left\{
\begin{matrix}
y' = 5y + 7x^2 + 3x + 2\\
y(0) = 1
\end{matrix}
\right.$$ a) Aproxime $y(1)$ pelo Método de Euler, com $h = 1$.

b\) Aproxime $y(1)$ pelo Método de Runge-Kutta de 4ª ordem, com $h = 1$.


