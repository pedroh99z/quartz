
# ⚠️ AVISO

Este resumo foi feito durante o meu doutorado, como parte de um seminário da disciplina de Álgebra Comutativa, sobre Ideais Primários. Trata-se de um roteiro da apresentação, e também um material sobre o tema, que depois foi disponibilizado para os colegas. Originalmente, este texto foi escrito em *latex*. A versão que estou apresentando aqui foi convertida automaticamente de latex para *markdown* pelo programa *pandoc*, e pode conter erros de formatação. 

# Ideais Primários

 {#id_primario .definicao}
**Definição 1**. *Um ideal $Q \in \mathcal{I}(R)\backslash\{ R \}$ é
chamado primário se $\alpha \beta \in Q$ e $\alpha \notin Q$, então
$\beta^n \in Q$ para algum $n \in \mathbb{N}^*$, isto é,
$\beta \in \sqrt{Q}$.*



**Observação 2**. *A Definição [1](#id_primario){reference-type="ref"
reference="id_primario"} equivale a dizer que um ideal
$Q \in \mathcal{I}(R)\backslash\{ R \}$ é chamado primário se
$\alpha \beta \in Q$ e $\alpha,\beta \notin Q$, então
$\alpha, \beta \in \sqrt{Q}$.*



**Exemplo 3**. *Todo ideal primo é um ideal primário. Em particular,
todo ideal maximal é primário.*


De fato, seja $I \subseteq R$ um ideal primo de $R$. Por definição,
dados $a, b \in R$ tais que $ab \in I$, com $a \notin I$, temos que
$b \in I$. Logo, $b \in \sqrt{I}$, donde segue que $I$ é um ideal
primário. Por fim, como todo ideal maximal é primo, segue que todo ideal
maximal é um ideal primário. Temos então a seguinte inclusão:
$$\{ M \in \mathcal{I}(R);\ M \text{ é maximal} \} \subseteq Spec(R) \subseteq \{ Q \in \mathcal{I}(R);\ Q \text{ é primário} \}.$$


**Exemplo 4** (Ideal primário que não é primo). *O ideal
$I = \langle 4 \rangle$ do anel $\mathbb{Z}$ é primário, mas não é
primo.*


Primeiramente, note que $I$ não é primo, pois $2 \cdot 2 \in I$, mas
$2 \notin I$. Agora, suponha que $ab \in I$, com $a \notin I$. Veja que
4 precisa ter ao menos um fator primo em comum com $b$, pois caso
contrário, 4 dividiria $a$, implicando que $a \in I$. Como $4 = 2^2$,
segue que $b$ é múltiplo de 2. Consequentemente, $b^2$ deve ser múltiplo
de 4, implicando que $b \in I$. Deste modo, $I$ é um ideal primário.

 {#prop-4-1 .proposicao}
**Proposição 5**. *Um ideal $I \in \mathcal{I}(R) \backslash\{R\}$ é
primário se, e somente se todo divisor de zero em $\dfrac{R}{I}$ é
nilpotente.*



*Proof.* Seja $r + I \in \dfrac{R}{I}$ um divisor de zero, ou seja,
$r + I \neq I$ e existe $s + I \neq I$, $s \in R$, tal que
$I = (r+I) (s + I) = rs + I$. Como $s \notin I$ e $I$ é primário, segue
que $r^n \in I$, para algum $n \in \mathbb{N}^*$. Assim,
$(r + I)^n = I$, e consequentemente $r + I$ é nilpotente.

Reciprocamente, suponha que $rs \in I$, mas $r, s \notin I$. Novamente,
temos que $I = rs + I = (r+I) (s+I)$. Neste caso, $r+I$ e $s + I$ são
divisores de zero em $\dfrac{R}{I}$. Por hipótese, temos que $r + I$ e
$s + I$ são nilpotentes, isto é, $(r+I)^n = I$ e $(s + I)^m = I$, para
alguns $n, m \in \mathbb{N}^*$. Como consequência, temos $I = r^n + I$ e
$I = s^m + I$, implicando que $r^n, s^m \in I$, isto é,
$r, s \in \sqrt{I}$. Portanto, $I$ é primário. ◻



**Observação 6**. *A extensão de um ideal primário nem sempre é um ideal
primário. De fato, considere o homomorfismo
$\varphi : \mathbb{Z}\to \mathbb{Z}_6$ tal que
$\varphi (x) = \overline{x}$. Temos que o ideal nulo $\{ 0 \}$ é
primário, pois $\mathbb{Z}$ é um domínio, o que implica que $\{ 0 \}$ é
primo. No entanto,
$\{ 0 \}^e = \langle \varphi (\{ 0 \}) \rangle = \langle \{ \overline{0} \} \rangle = \{ \overline{0} \}$
não é primário, uma vez que
$\overline{2} \cdot \overline{3} \in \{ \overline{0} \}$, mas
$\overline{2}$ e $\overline{3}$ não são elementos de
$\{ \overline{0} \}$ e
$overline{2}, \overline{3} \notin \sqrt{\{ \overline{0} \}}$. No
entanto, temos que a contração de um ideal primário é primário, como
mostra o resultado a seguir.*



**Proposição 7**. *Seja $\varphi : R \to S$ um homomorfismo de anéis e
$Q \in \mathcal{I}(S) \backslash\{S\}$ um ideal primário, então
$Q^c \in \mathcal{I}(R)$ é primário.*



*Proof.* Primeiramente, note que $Q^c \neq R$, pois caso contrário,
teríamos que $1 \in R = Q^c$, e como $\varphi$ é um homomorfismo,
seguiria que $\varphi(1) = 1 \in Q$, já que $Q = \varphi^{-1} (Q)$.

Agora, seja $rs \in Q^c$, com $r \notin Q^c$. Por definição,
$\varphi(rs) \in Q$, e consequentemente, $\varphi(r) \varphi(s) \in Q$.
Se $r \notin Q^c$, então $\varphi(r) \notin Q$. Neste caso, como $Q$ é
primário, segue que $\varphi(s) \in \sqrt{Q}$. Em outras palavras,
$\varphi(s)^n \in Q$, para algum $n \in \mathbb{N}^*$. Consequentemente,
$s^n \in Q^c$, pois $\varphi$ é um homomorfismo. Assim, $Q^c$ é
primário. ◻


 {#obs-ideal-primo .obs}
**Observação 8**. *Em geral, dado um ideal $I$, temos que
$I \subseteq \sqrt{I}$. No caso em que $I$ é um ideal primo, temos
também a inclusão contrária, e portanto vale que $\sqrt{I} = I$.*


 {#id_primario_raiz_prima .proposicao}
**Proposição 9**. *Seja $Q \in \mathcal{I}(R)$ um ideal primário. Temos
que $\sqrt{Q} = P \in Spec(R)$. Além disso, $Min(Q) = \{P\}$.*



*Proof.* Primeiramente, vamos provar que $\sqrt{Q} \neq R$. De fato, se
$1 \in \sqrt{Q}$, então $1 \in Q$, implicando que $Q = R$, o que não
pode ocorrer, pois $Q$ é primário. Portanto, $\sqrt{Q} \neq R$.

Agora, provemos que $\sqrt{Q}$ é primo. Seja $rs \in \sqrt{Q}$, com
$r \notin \sqrt{Q}$. Por definição, existe $n \in \mathbb{N}^*$ tal que
$(rs)^n \in Q$. Assim, $r^n s^n \in Q$. Uma vez que $r \notin \sqrt{Q}$,
segue que $r^n \notin Q$. Como $Q$ é primário, devemos ter que
$(s^n)^m \in Q$, para algum $m \in \mathbb{N}^*$. Deste modo,
$s \in \sqrt{Q}$. Assim, $\sqrt{Q}$ é primo, isto é,
$\sqrt{Q} \in Spec(R)$.

Por fim, mostremos que $Min(Q) = \{P\}$. Note que $P \in Var(Q)$, pois
$Q \subseteq \sqrt{Q} = P$. Seja $P' \in Var(Q)$, isto é, $P'$ é um
ideal primo contendo $Q$. Temos que
$$P = \sqrt{Q} \subseteq \sqrt{P'} = P',$$ onde a última igualdade
decorre da Observação [8](#obs-ideal-primo){reference-type="ref"
reference="obs-ideal-primo"}. Assim, $Min(Q) = \{P\}$. ◻



**Observação 10**. *Um ideal primário $Q$ satisfazendo
$\sqrt{Q} = P \in Spec(R)$ é dito **$P$-primário**.*



**Lema 11**. *Sejam $P \in Spec(R)$ e $Q_1, \dots, Q_n$ ideais
$P$-primários de $R$, temos que $Q = \cap_{i=1}^n Q_i$ é $P$-primário.*



*Proof.* Primeiramente, observe que
$$\sqrt{Q} = \sqrt{\cap_{i=1}^n Q_i} = \cap_{i=1}^n \sqrt{Q_i} = \cap_{i=1}^n P = P.$$
Ainda, como cada $Q_i$ é primário, $i = 1,2, \dots, n$, segue que
$Q = \cap_{i=1}^n Q_i \neq R$. Agora, para todo $rs \in Q$, com
$r \notin Q$, temos que $rs \in Q_i$, para todo
$i \in \{1,2, \dots, n\}$, e $r \notin Q_j$, para algum
$j \in \{1,2,\dots,n\}$. Como $Q_j$ é $P$-primário, segue que
$$s \in \sqrt{Q_j} = P = \sqrt{Q},$$ e consequentemente, $Q$ é
$P$-primário. ◻



**Teorema 12**. *Se $I \in \mathcal{I}(R) \backslash\{ R \}$ é tal que
$\sqrt{I} = M$ é um ideal maximal, então $I$ é $M$-primário.*



*Proof.* Considere o homomorfismo canônico
$\varphi : R \to \dfrac{R}{I}$ definido $\varphi (r) = \overline{r}$, o
qual sabemos que é sobrejetor. Observe que 
{eq_4-1}
$$
    M = \sqrt{I} = \sqrt{ \{ \overline{0} \}^c} = \left( \sqrt{ \{ \overline{ 0 } \} } \right)^c.
$$
Como para todo homomorfismo sobrejetor temos que a imagem de um ideal é
um ideal, segue que $\varphi (M) = \dfrac{M}{I}$ é um ideal de
$\dfrac{R}{I}$. Além disso, segue do fato de $M$ ser maximal que
$\dfrac{R}{M}$ é corpo. Consequentemente, temos que $\dfrac{M}{I}$ é
maximal, já que $$\dfrac{\frac{R}{I}}{\frac{M}{I}} \cong \dfrac{R}{M}.$$
Em outras palavras,
$M^e = \langle \varphi(M) \rangle = \varphi(M) = \dfrac{M}{I}$ é um
ideal maximal de $\dfrac{R}{I}$.

Agora, por ([\[eq_4-1\]](#eq_4-1){reference-type="ref"
reference="eq_4-1"}) e do fato de $\varphi$ ser sobrejetora, temos que
$$M^e = \left(  \left( \sqrt{ \{ \overline{0} \} }\right)^c \right)^e = \sqrt{ \{ \overline{0} \} } = \bigcap_{\overline{P} \in Spec \left(\frac{R}{I}\right)} \overline{P}.$$
Consequentemente, $M^e \subseteq \overline{P}$, para todo
$\overline{P} \in Spec\left( \dfrac{R}{I}\right)$. Uma vez que $M^e$ é
um ideal maximal, segue que
$Spec\left( \dfrac{R}{I}\right) = \{ M^e \}$.

Agora, dado $\overline{r} \in \dfrac{R}{I}$ um divisor de zero, temos
que $\overline{r}$ não é invertível. De fato, se $\overline{r}$ fosse
invertível, existiria $\overline{t} \in \dfrac{R}{I}$ não nulo tal que
$\overline{r} \overline{t} = 1$. Como $\overline{r}$ é um divisor de
zero, existe $\overline{s} \in \dfrac{R}{I}$, com
$\overline{s} \neq \overline{0}$ tal que
$\overline{r} \overline{s} = 0$. Neste caso,
$\overline{0} = \overline{s} \overline{r} \overline{t} = \overline{s} \neq \overline{0}$,
o que é um absurdo. Logo $\overline{r}$ não pode ser invertível.

Da teoria de ideais maximais, temos que todo elemento não invertível
pertence a um ideal maximal. Como todo ideal maximal é primo, e o único
ideal primo de $\dfrac{R}{I}$ é $M^e$, segue que
$\overline{r} \in M^e = \sqrt{\{\overline{0}\}}$. Em outras palavras,
$\overline{r}$ é nilpotente. Assim, pela Proposição
[5](#prop-4-1){reference-type="ref" reference="prop-4-1"}, temos que $I$
é primário. ◻



**Corolário 13**. *Se $M$ é um ideal maximal, então $M^n$ é $M-$primário
para todo $n \in \mathbb{N}^*$.*



*Proof.* Como todo ideal maximal é primo, vale a inclusão
$\sqrt{M^n} \subseteq M$. Como $M \subseteq \sqrt{M^n}$ é imediato,
segue que $\sqrt{M^n} = M$. Pelo Teorema anterior, temos que $M^n$ é
$M$-primário. ◻



**Exemplo 14** (Ideal primário que não é potência de um maximal). *O
ideal $\langle X, Y^2 \rangle \subseteq \mathbb{K} [X, Y]$ é
$\langle X, Y \rangle$-primário.*


De fato, veja que
$$(\langle X, Y \rangle)^2 = \langle X^2, XY, Y^2 \rangle \subsetneq \langle X, Y^2 \rangle \subsetneq \langle X, Y \rangle.$$
Ainda, 
{eq_sanduiche}
$$
\sqrt{(\langle X, Y \rangle)^2} \subseteq \sqrt{\langle X,Y^2 \rangle} \subseteq \sqrt{\langle X,Y \rangle}.
$$
Como $\langle X, Y \rangle$ é um ideal maximal, vimos na demonstração do
corolário anterior que
$\sqrt{(\langle X,Y \rangle)^n} = \langle X,Y \rangle$, para todo
$n \in \mathbb{N}^*$. Assim sendo, temos de
([\[eq_sanduiche\]](#eq_sanduiche){reference-type="ref"
reference="eq_sanduiche"}) que
$\sqrt{\langle X, Y^2 \rangle} = \langle X, Y \rangle$.

Portanto, $\langle X, Y^2 \rangle$ é um ideal
$\langle X, Y \rangle$-primário. Vejamos que ele não é potência de um
ideal maximal. Suponha, por absurdo, que exista $n \in \mathbb{N}^*$ tal
que $\langle X, Y^2 \rangle = M^n$, para algum ideal maximal $M$. Como
$M$ é um ideal maximal, temos da demonstração do corolário anterior que
$\sqrt{M^n} = M$. Consequentemente,
$$\langle X, Y \rangle = \sqrt{ \langle X, Y^2 \rangle } = \sqrt{M^n} = M.$$
Em outras palavras,
$$\langle X, Y^2 \rangle = (\langle X, Y \rangle)^n$$ No entanto, a
igualdade acima não pode ser verdadeira. De fato, quando $n = 1$, já
observamos que $\langle X, Y^2 \rangle \subsetneq \langle X, Y \rangle$.
Para $n > 1$, temos que $x \in \langle X, Y^2 \rangle$, mas
$x \notin (\langle X, Y \rangle)^n$. Desse modo, o ideal primário
$\langle X, Y^2 \rangle$ não é potência de um ideal maximal.
