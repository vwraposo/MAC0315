# MAC 0315 - Otimização Linear
##### Leônidas - Sala

##### Bibliografia:
*  

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

    Vamos provar por contradição. Supondo que $\{b\}\cup\{a^j\}^n_{j=2}$ seja $l.d.$ podemos escrever $b$ da seguinte forma:
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

---
# Aula 2 - 9/3

**Teorema Fundamental da Indução:**

\[
    T(n) \text{ vale } (n \in \mathbb{N}) \\
    H_0(\text{base}):T(n_0) \text{ vale } (n_0 \in \mathbb{N}) \\
    H_1(\text{paso}):n \geq n_0, T(n) \text{ vale } \Rightarrow T(n+1) \text{ vale} \\
    \text{Então } T(n) \text{ vale } \forall n \geq n_0
\]

Dem.:

Supor por constradição que existe $n \geq n_0: T (n)$ não vale.

Então $\exists \overset{\_}{n} > n_0$, primeiro tal que $T(\overset{\_}{n})$ não vale. Como $\overset{\_}{n}  > n_0 \Rightarrow \overset{\_}{n}-1 \geq n_0$ e $\overset{\_}{n} - 1 \in \mathbb{N}$ de tal modo que $T(\overset{\_}{n}-1)$ vale.
Por outro lado $H_1$ se aplica e teriamos $T(\overset{\_}{n}-1 + 1) = T(\overset{\_}{n}) vale.
