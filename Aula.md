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
