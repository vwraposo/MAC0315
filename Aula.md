# MAC 0315 - Otimização Linear
##### Leônidas - Sala

##### Bibliografia:
*  Linear Otimizationn, Bertisimas

##### Informações
* Comunicação e informação:
* 2 Avaliações e 1 Sub Aberta

---

# Aula 1 - 7/3

Relembrar Algelin:

1. Espaço Vetorial:
\[
    E : \forall (\alpha, \beta) \in E \times E \Rightarrow
    \begin{cases}
        \alpha + \beta \in E \\
        \theta.\alpha \in E & \forall \theta \in \mathbb {R}
    \end{cases}
\]


1. T : $\mathbb{R}^n \rightarrow \mathbb{R}^n$ é uma transformação linear $\Leftrightarrow$

\[
        \forall (\alpha, x, y) \in \mathbb{R} \times \mathbb{R}^n \times \mathbb{R} \Rightarrow
        \left.
        \begin{array}{lr}
            T(x+y) = T (x) + T(y) \\
            T(\alpha.x) = \alpha.T(x)
        \end{array}
        \right.
\]

1. Linearmente Independente:
    \[
        \{a^i\}^{n}_{i = 1} \text{l.i} \Leftrightarrow\\
        \forall \lambda \in \mathbb{R}^n :
         \sum^{n}_{i = 1} \lambda_i.a^i = 0 \Rightarrow \lambda = 0
    \]

2. Linearmente Dependente:
    \[
        \{a^i\}^{n}_{i=1} \text{l.d} \Leftrightarrow \\
        \exists \lambda \in \mathbb{R}^n : \sum^{n}_{i=1}\lambda_i.a^i = 0 \  \text{and} \ \lambda \neq 0
    \]

3. Prove que:
\[
    \left.
    \begin{array}{lr}
    \{a^i\}^n_{i=1} \ \text{l.i} \\ b=\sum^n_{i = 1}\alpha_i.a^i \ com \ \alpha_1 \neq 0
    \end{array}
    \right\}
    \Rightarrow \{b\} \cup \{a^j\}^n_{j=2} \ l.i.
\]

    * Vamos provar por contradição. Supondo que $\{b\}\cup\{a^j\}^n_{j=2}$ seja $l.d.$ podemos escrever $b$ da seguinte forma:
\[
    b = \sum^n_{i = 2}\lambda_i.a^i \quad  \lambda \in \mathbb{R}^{n-1}
\]
    Expandindo b obtemos:
\[
    b = \sum^n_{i = 1}\alpha_i.a^i = \alpha_1.a^1 + \sum^n_{i = 2}\alpha_i.a^i = \sum^n_{i = 2}\lambda_i.a^i
\]
    Isolando $a^1$ chegamos em uma contradição, observando que $\alpha_1 \neq 0$
\[
    a^1 = \frac{1}{\alpha_1} . \left(\sum^n_{i = 2}\lambda_i.a^i - \sum^n_{i = 2}\alpha_i.a^i \right) = \frac{1}{\alpha_1} . \sum^n_{i = 2}(\lambda_i - \alpha_i)a^i
\]
    já que  $\{a^i\}^n_{i=1}$ é $l.i.$ não é possível escrever um termo como combinação linear dos outros (Teorema). $\blacksquare$

    * Prova direta
    \[
        \left(\{z^i\}_{i\in I} \quad l.i. \Leftrightarrow \forall \beta:\sum \beta_i.z^i = 0 \Rightarrow \beta = 0 \right)
    \]

    Seja $\beta$:

    \[
        0 = \beta_1.b + \sum^k_{j=2}\beta_j.a^j =  \sum^k_{j=1}\beta_1.\alpha_i.a^i + \sum^k_{j=2}\beta_j.a^j =  \\
        \underbrace{\beta_1.\alpha_1}_{\theta_1}.a^1 + \sum^k_{j=2}\underbrace{(\beta_1.a^j + \beta_j)}_{\theta_j}.a^j \\\Rightarrow \theta_j = 0 \\
        \Rightarrow 0 = \theta_1 = \beta_1.\alpha_1 \underset{\alpha_1 \neq 0}{\Rightarrow} \beta_1 = 0 \\
        \Rightarrow \beta_j= \beta_i.\alpha_j + \beta_j = \theta_j = 0 \\
        \Rightarrow \{b\} \cup \{a^j\}^n_{j=2} \ l.i. \blacksquare
    \]

---

# Aula 2 - 9/3

Terminamos a prova do terceiro exercício da aula anterior.


**Teorema Fundamental da Indução:**

> Podemos tomar a _indução_ como axioma e provar o teorema da _boa ordem_. Mas aqui faremos o contrário.

\[
    T(n) \text{ vale } (n \in \mathbb{N}) \\
    H_0(\text{base}):T(n_0) \text{ vale } (n_0 \in \mathbb{N}) \\
    H_1(\text{passo}):n \geq n_0, \ T(n) \text{ vale } \Rightarrow T(n+1) \text{ vale} \\
    \text{Então } T(n) \text{ vale } \forall n \geq n_0
\]
Dem:

Supor por contradição que existe $n \geq n_0: T (n)$ não vale.

Então $\exists \overset{\_}{n} > n_0$, primeiro tal que $T(\overset{\_}{n})$ não vale. Como $\overset{\_}{n}  > n_0 \Rightarrow \overset{\_}{n}-1 \geq n_0$ e $\overset{\_}{n} - 1 \in \mathbb{N}$ de tal modo que $T(\overset{\_}{n}-1)$ vale.
Por outro lado $H_1$ se aplica e teriamos $T(\overset{\_}{n}-1 + 1) = T(\overset{\_}{n})$ vale.

**Otimização** (Programação):

\[
min\left\{\varphi(c): x \in \Omega\right\} \text{ ou }
    max\left\{\varphi(c): x \in \Omega\right\}
\]

$\varphi ()$ - Função Objetivo

$x \in \Omega$ : pontos notáveis

Exemplos:

1. $min\left\{ x^2 : x \in \mathbb{R}\right\}$ (convexa)

2. $min\left\{x^2 + y^2 : (x, y) \in \mathbb{R}^2\right\}$ (concava)

3. $min \left\{x+y : x.y = k, (x, y) \geq O\right\} (k \in \mathbb{R}^{* }))$
4. $\{P^i\}^3_{i=1} \subseteq \mathbb{R}^2$

    $min \left\{\sum^3_{i=1} || P^i - P ||^2:P \in \mathbb{R}^2\right\}$ (Baricentro do Triangulo)

    $min \left\{\sum^3_{i=1} || P^i - P ||:P \in \mathbb{R}^2\right\}$  (Ponto de Fermat)

Obs.:

\[
    \Lambda := argmin \{\varphi (x) : x \in \Omega\} \\
    \quad \quad := \{\overset{\_}{x} : \varphi(\overset{\_}{x})\leq \varphi (x), \forall x \in \Omega\} \\
    \\
    \underbrace{min\{\varphi(x):x \in \Omega\}}_{\Lambda \text{ é a solução  de } \varphi}\equiv \underbrace{max\{-\varphi(x):x \in \Omega\}}_{\overline{\Lambda} \text{ é a solução  de } -\varphi} \\
    \Leftrightarrow \overline{x} \in \Lambda \Leftrightarrow \overline{x} \in \overline{\Lambda}
\]

---

# Aula 3 - 14/03

\[
    min\{\varphi(x): x \in \Omega\} \equiv  - max\{-\varphi(x):x \in \Omega\} \\
\]

Usando essa equivalência conseguimos o mesmo conjunto solução e mesmo valor ótimo.

\[
    Co \rightleftarrows^1_2 Cm \\
    \downarrow \quad \quad \quad \downarrow \\
    So \  \leftarrow  \ Sm
\]

Co - Conjunto original

1 = $T$ - Transformação

2 = $T^{-1}$ - Transformação inversa

Cm - Conjunto modificado

Sm - Conjunto solução do conjunto modificado

So - Conjunto solução do conjunto original

**Objetivo do Curso**

Teoria $\rightarrow$ Simplex
\[
    min\{c'x : A.x = b, x \geqq 0\}
\]
Obs:
\[
    \begin{array}{lr}
        x \in \mathbb{R}^n \\
        x \geqq 0 \Leftrightarrow x_i > 0 \text{ ou } x_i = 0, \forall i \\
        x \geq 0 \Leftrightarrow x \geqq 0 \text{ e } x !=  0 \\
        x > 0 \Leftrightarrow x_i > 0, \forall i
    \end{array}
\]

---

# Aula  16/03

#### Problema:

\[
    min\{c'x : A.x = b, x \geqq 0\}
\]

Restrições lineares:
\[
    a^ix \leqq b_i \rightarrow Ax \leqq b\\
    a^ix  = b_i \rightarrow Ax = b\\
    a^ix \geqq b_i \rightarrow Ax \geqq b
\]

Queremos mostrar que é possivel escrever um problema como um problema equivalente com uma restrição diferente ($\leqq, =, \geqq$)

Exemplo:

\[
    Ax = b \\
    x \geqq 0 \Leftrightarrow Ix \geqq 0 \Leftrightarrow -Ix \leqq 0
\]

\[
    Ax = b \Leftrightarrow
    \begin{cases}
        Ax \leqq b\\
        Ax \geqq b \Leftrightarrow -Ax \leqq -b
    \end{cases} \\
\]
\[
    \left.\begin{array}{lr}
        Ax = b \\
        x \geqq 0
    \end{array}\right\} \equiv
    \left[\begin{array}{lr}
        A \\
        -A \\
        -I
    \end{array}\right] x \leqq
    \left[\begin{array}{lr}
        b \\
        -b \\
        0
    \end{array}\right]
\]
$Ax \leqq b \leftrightarrow Ax = b , x \geqq 0$
\[
    x: Ax \leqq b \Rightarrow c - Ax \geqq 0 \\
    z:= b-Ax \geqq 0 \\
    Ax + Iz = b \\
    [A|I]\left[\begin{array}{lr}
        x \\
        z
    \end{array}\right] = b, \quad z \geqq 0
\]

Subproblema, para de um problema de igualdade $Ax = b$ obter $x \geqq 0$
\[
    \alpha \in \mathbb{R} \rightarrow \left(\begin{array}{lr}\alpha^+ \\ \alpha-\end{array}\right) \\
    \alpha^+ := \alpha, \quad \alpha \geqq 0 \ \text{ ou } \ 0, \quad \alpha < 0\\
    \alpha^- := -\alpha, \quad \alpha < 0  \\text{ ou } \ 0, \quad \alpha \geq 0 \\
    [A|-A]\left[\begin{array}{lr}
        x^+ \\
        x^-
    \end{array}\right] = b, \quad (x^, x^-) \geqq 0
\]
Obs: Propriedades do operador $\alpha^+$ e $\alpha^-$

\[
    \alpha^+ - \alpha^- = \alpha \\
    \alpha^+ + \alpha^- = |\alpha|
\]

---

# Aula 21/03

Exemplo: $max \ (-1, -1)x$
\[
    (0, 1) x \leq 1 \\
    (1, 1) x \leq 2 \\
    (1, 0) x \leq 2 \\
    x \geq 0
\]

### Definições

**Hiperplano:** $\mathcal{H}_{c, \alpha} := \{x:c'x = \alpha \}$

**Semi-espaço:** $\mathcal{S}_{c, \alpha} := \{x:c'x \leq \alpha \}$

**Poliedro:** interceção de um número finitos de hiperplanos e semi-espaços.

**Contra-exemplo:** $C := \cap\mathcal{S}_{x, r}, x \in \{ x: ||x||^2 = r\}$

Um círculo, que possui infinitos pontos,sendo impossível verificar todos

Exemplos:

1. $\mathbb{R}^n$
2. $\varnothing$
3. $X := \{x: Ax = b, x \geqq 0\}$
4. Bola fechada de norma 1

**Conjunto convexo:** $A$ é convexo $\Leftrightarrow \forall (a^1, a^2, \lambda) \in A\times A\times [0, 1] \Rightarrow a_\lambda := \lambda a^1 + (1-\lambda)a^2 \in A$

> Obs: pensar no vetor $a^1 - a^2$, então $x_\lambda := a^2 + \lambda(a^1 - a^2)$

Exemplos:

1. $H_{c,\alpha}$

\[
    \forall (x^1, x^2, \lambda) \in H_{c,\alpha} \times H_{c,\alpha} \times [0, 1] \\
    x_\lambda := \lambda x^1 + (1-\lambda)x^2 \\
    c'x_\lambda = c' (\lambda x^1 +  (1 - \lambda)x^2) = \\
    \lambda.c'x^1 + (1-\lambda)c'x^2 = \lambda\alpha + (1-\lambda)\alpha = \alpha_\blacksquare
\]

2. $S_{c,\alpha}$

\[
    \forall (x^1, x^2, \lambda) \in S_{c,\alpha} \times S_{c,\alpha} \times [0, 1] \\
    x_\lambda := \lambda x^1 + (1-\lambda)x^2 \\
    c'x_\lambda = c' (\lambda x^1 +  (1 - \lambda)x^2) = \\
    \lambda.c'x^1 + (1-\lambda)c'x^2 \\
    0 \leqq \lambda \leqq 1 \Rightarrow c'x_\lambda \leq \lambda\alpha + (1-\lambda)\alpha \leq \alpha_\blacksquare
\]

3. $X$ é convexo
\[
    X := \{x: Ax = b, x \geqq 0\} \\
    \forall (x^1, x^2, \lambda) \in X\times X \times [0, 1] \\
    x_\lambda := \underbrace{\lambda x^1}_{\geqq 0} + \underbrace{(1 - \lambda)x^2}_{\geqq 0} \geqq 0\\
    Ax_\lambda = A(\lambda x^1 + (1 - \lambda)x^2) = \lambda Ax^1 + (1 - \lambda)Ax^2 \\
    \lambda b + (1 - \lambda) b = b_{\ \blacksquare}
\]

4. $B:= \{x: ||x - \overset{\_}x|| \leqq \Gamma\} (\overset{\_}x\in \mathbb{R}^n )(\Gamma \in \mathbb{R}_{++})$

> Norma \
> 1. $||x|| \geqq 0$ \
> 2. $||\lambda x|| = |\lambda|||x||$ \
> 3. $|| x + y|| \leqq ||x|| + ||y||$


\[
    \forall(x^1, x^2, \lambda)\in B \times B \times [0, 1] \\
    x_\lambda := \lambda x^1 + (1 - \lambda)x^2 \\
    ||\lambda x^1 + (1 - \lambda)x^2 - \overset{\_}x|| = ||\lambda x^1 + (1 - \lambda)x^2 - \lambda \overset{\_}x - (1 - \lambda)\overset{\_}x|| =  \\
    ||\lambda (x^1 - \overset{\_}x) + (1 - \lambda)(x^2 - \overset{\_}x)|| \leqq ||\lambda (x^1 - \overset{\_}x)|| + ||(1 - \lambda)(x^2 - \overset{\_}x)|| = \\
     \lambda ||(x^1 - \overset{\_}x)|| + (1 - \lambda)||(x^2 - \overset{\_}x)|| \leqq \lambda \Gamma + (1 - \lambda)\Gamma = \Gamma_{\ \blacksquare}
\]
