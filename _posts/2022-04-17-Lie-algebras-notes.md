---
layout: article
title: Lie algebras notes
tags: notes
aside:
  toc: true
mathjax: true
---

# Lie algebras

*Disclaimer: This set of notes are based on the 2021 undergrad lecture series taught by Dr Adam Thomas (Warwick); the main textbook is Erdmann & Wildon's [Introduction to Lie algebras](https://link.springer.com/book/10.1007/1-84628-490-2). There are places where things are incomplete and left as placeholders.* 

# Engel's theorem

(Converse to the fact that a nilpotent element is ad-nilpotent.)

## Setup:

## Lemma

Let $V$ be a vector space and $L$ a subalternstes of $\mathrm{gl}(V)$. If $x \in L$ is nilpotent, then it is ad-nilpotent.

*Proof.* Since $x$ is nilpotent, there exists an $m \in \mathbb{N}$ such that $x^m = 0$ (def). Let $y \in L$ and consider $\mathrm{ad}(x)^{2m}(y) = [x, [x, [\dots, [x, y]] \dots]$. Compute this and check (by induction) that it equals

$$
\sum_{i = 0}^{2m} c_i x^i y x^{2m - i}.
$$

In particular, this equals $0$ since if $i \le m - 1$ then $2m - i > m$ and $x^i y x^{2m-i} = 0$ , similarly if $i > m - 1$ then $x^i = 0$. Hence, $\mathrm{ad}(x)^{2m}(y) = 0 \ \forall y \in L$.                                                                          $\square$

## Proposition

Let $V$ be a vector space, $L$ a subalgebra of $\mathrm{gl}(V)$ such that every element $x \in L$ is nilpotent. Then there exists a vector $v \in V \backslash\{0\}$ such that $x(v) = 0$ for all $x \in L$.

*Proof.* Induction on dimension of $L$. If dim($L$) is 1 then $L = \langle y \rangle$ for some $y \in L \backslash \{0\}$. Since $y \neq 0$ is nilpotent, there is some $m > 0$ such that $y^m = 0$ and $y^{m-1} \neq 0$. So $\exists w \in V$ such that $y^{m-1}(w) \neq 0$. Let $v = y^{m-1}$, then $v$ is an eigenvalue of $y$. If $x \in L$, then $x = a_x y$ for some $a_x \in \mathbb{F}$ and so $x(v) = a_xy(v) = 0$ (base case).

Now suppose that $L$ has dim $n > 1$ and that the result holds for all Lie algebras of dimension less than $n$. Let $M$ be a maximal proper Lie subalgebras of $L$.  (Exists since $L$ is finite-dimensional)

Define a map $f \colon M \to \mathrm{gl}(L/M)$ by $f(m)(y + M) = [m, y] + M$ for all $m \in M, y \in L$. (Check this is well-defined!)

Moreover, bilinearity of Lie bracket implies that $f(m) \in \mathrm{gl}(L/M)$ and $f$ is a linear map.

Using the Jacobi identity:

$$
[f(a), f(b)](y + M) = f(a)f(b) (y+m) - f(b)f(a)(y + M) = ([a, [b, y]] + M - [b, [a, y]] + M) = ([a, [b, y]] + [b, [y, a]]) + M = -([y, [a, b]] + M) = [[a, b], y] + M = f([a, b])(y + M).
$$

So $f$ is a Lie algebra homomorphism. Then $f(M)$ is a Lie subalgebra of $\mathrm{gl}(L/M)$ and $\dim f(M) \le \dim M < \dim L = n.$ Since for all $m \in M \le L$ , $m \in L$, we have that $m$ is nilpotent and ad-nilpotent by the previous lemma. That is, there is some $k \in \mathbb{N}$ such that $\mathrm{ad}(m)^k = 0$. Now we want to verify that $f(m)$ is also nilpotent: $f(m)^k(y + M) = [m, [m, \dots, [m, y]]\dots] + M = \mathrm{ad}(m)^k(y) + M = M$. Therefore, $f(m)$ is nilpotent (as a linear map $L/M \to L/M$. So apply the inductive hypothesis to $f(M) \le \mathrm{gl}(L/M)$  there exists some $z \in L\backslash M$ such that $f(m)(z + M) = M$ for all $m \in M$.

By construction, $f(m)(z + M) = [m, z] + M$, so it follows that $[m, z] \in M$ for all $m \in M$. Next consider $L_0 = \langle M, z \rangle_{\mathbb{F}} = M \oplus \langle z \rangle_{\mathbb{F}}$ since $z \notin M$. ($L_0$ has one more dimension than M.) That is, if $a, b \in L_0$, then $a = m_a + \alpha z$, $b = m_b + \beta z$ for some $m_a, m_b \in M, \alpha, \beta \in \mathbb{F}$. Thus, $[a, b] = [m_a, m_b] + \alpha[z, m_b] + \beta[m_a, z] \in M$ since every summand is in $M$. Thus $L_0$ is a subalgebra of $L$, which properly contains $M$. By maximality of $M$, it follows that $L_0 = L$. So since $[m_a + \alpha z, m] \in M$ for all $m \in M$, we see that $M$ is an ideal of $L$ and has dimension one lower than $L$.

We can now apply the inductive hypothesis to $M \le \mathrm{gl}(V)$. Then there exists a nonzero vector $w \in V$ such that $m(v) = 0$ for all $m \in M$. Consider the 0-weight space,

$$
W = \{u \in V \mid m(u) = 0 \ \forall m \in M\}.
$$

Then $W \neq \{0\}$ since $w \in W$. In particular, this implies that $W$ is $L$-invariant. Thus, $z(u) \in W$ for all $u \in W$ for $z \in L$. Given that $z$ is nilpotent, there exists some $\ell \in \mathbb{N}$ such that $z^{\ell - 1} \neq 0,\ z^\ell = 0$. Then we have $0 \neq v = z^{\ell-1} \in W$ such that $z(v) = 0$. Now, for $x \in L$, we have $L = L_0 = \langle M, z\rangle_{\mathbb{F}}$, so $x  = m_x + \alpha z$ and $x(v) = m_x(v) + \alpha z(v) = 0$ since $m_x(v) = 0$ as $v \in W$, the 0-weight space, and $z(v) = 0$ by the choice of $v$.                                                                                                                $\square$

## Theorem (Engle's theorem for subalgebras of $\mathrm{gl}(V)$

Let $L$ be a subalgebra of $\mathrm{gl}(V)$. Suppose that every elt of $L$ is nilpotent. Then there exists a basis of $V$ such that the matrix of every elt of $L$ is strictly upper triangular wrt this basis. In particular, $L$ is nilpotent.

*Proof.*  Suppose we have a such a basis $\mathcal{B}$ with $|\mathcal{B}| = n$. Then $L$ is isomorphic to a subalgebra of $\mathrm{u}_n(\mathbb{F})$ and the fact that $\mathrm{u}_n(\mathbb{F})$ is nilpotent implies that $L$ is nilpotent.

Induction on dimension of $L$:

$n = 1$: then $\mathrm{gl}(V) = \mathbb{F}$. The only nilpotent element of is $0$, trivially true.

$n \ge 2$: Suppose the statemnet holds for all dimensions up to $n - 1$, want to show that it also holds for $n$. From previous Lemmas, we know that there exists some nonzero vector $v \in V$ such that $x(v)  = 0 \ \forall x \in L$. Let $U = \langle v \rangle$ be the subspace generated over $\mathbb{F}$ and write $\overline{V} = V/U$ for the quotient space. For $x \in L$ define $\overline{x} \colon \overline{V} \to \overline{V}$ by $\overline{x}(w + U) = x(w) + U$. We check that this is a well-defined linear map, that is, $\overline{x} \in \mathrm{gl}(V)$.

This gives rise to a Lie algebra homomorphism

$$
\varphi \colon L \to \mathrm{gl}(\overline{V}), x \mapsto \overline{x}.
$$

Also, $\varphi(L)$ is a subalgebra of $\mathrm{gl}(\overline{V})$.

If $x^m = 0$ for some $m \in \mathbb{N}$ then $\overline{x}^m = 0$. This shows that every element of $\varphi(L)$ is nilpotent and since $\dim(\overline{V}) < \dim (V)$, we apply the inductive hypothesis to $\overline{V}$. In particular, it follows that there exists a basis $\{v_2 + U, v_3 + U, \dots, v_n + U\}$ of $\overline{V} = V/U$ such that $\overline{x}$ is represented by a a strictly upper triangular matrix for all $x \in L$.

Define $\mathcal{B} = \{v_1 = v, v_2, \dots, v_n\}$. Then this is a basis of $V$ and by construction $x(v_1) = 0, x(v_2) = a_{1, 2}v_1$ for some $a_{1, 2} \in \mathbb{F}$, $x(v_3) = a_{1, 3}v_1 + a_{2, 3}v_2$, $\dots$, with all $a_{i,j} \in \mathbb{F}$.

Thus the matrix of $x$ wrt $\mathcal{B}$ is strictly upper triangular.

## Theorem (Engel's theorem, general)

Let $L$ be a Lie algebra. If every $x \in L$ is ad-nilpotent, then $L$ is nilpotent.

*Proof.* Under the adjoint representation $\mathrm{ad} \colon L \to \mathrm{gl}(V)$, we know that $\mathrm{ad}(L) \le \mathrm{gl}(V)$. For all $x \in L$, we have that $\mathrm{ad}(x)$ is nilpotent by hypothesis. By previous theorem, it follows that $\mathrm{ad}(L)$ is nilpotent. Since $\mathrm{ad}(L) \cong L/\ker (\mathrm{ad}) = L/Z(L)$, and $L/Z(L)$ is nilpotent implies that $L$ is nilpotent (given $Z(L)$ is nilpotent).

---

# Lie's theorem

## Lemma

Let $L = \mathrm{b}_n(\mathbb{C})$, then $[L, L] = \mathrm{u}_n(\mathbb{C})$.

## Proposition

Let $V$ be a vector space over $\mathbb{C}$, $L$ a subalgebra of $\mathrm{gl}(V)$. If $L$ is solvable then there exists a nonzero vector $v \in V$ such that for every $x \in  L$ $\exists \lambda(x) \in \mathbb{C}$ such that $x(v) = \lambda(x)v$, that is, $v$ is an eigenvector of $L$.

*Proof.* Induction on $n = \dim L$.

$n = 1$: $\mathbb{F} = \mathbb{C}$ so we have $L = \langle y \rangle_{\mathbb{C}}$ for some $y$, and there exists nonzero $v \in V$ such that $y(v)  = \lambda(v)$ for $\lambda \in \mathbb{C}$ since $\mathbb{C}$ is algebraically closed. Since $L$ is generated by $y$, for any $x \in L$ we can write $x = a_x y$ and so $x(v) = a_x y (v) = (a_x \lambda)v$. Rewriting $\lambda(x) = a_x \lambda$, we are done.

$n \ge 2$: now suppose the statement holds true up to $n - 1$. Since $L$ is solvable, we know that $[L, L] \neq L$. Let $M$ be a vector subspace of $L$ with $\dim M = \dim L - 1$ and $[L, L] \subseteq M$. Then $M$ is an ideal of $L$.Moreover, $L = M \oplus \langle z \rangle$ for some $z \in L \backslash M$. Since $M$ is a subalgebra of $L$ it is also solvable, and we may apply the inductive hypothesis. That is, there exists some nonzero $w \in V$ such that $w$ is an eigenvector for $M$. Thus we have a weight $\lambda \colon M \to \mathbb{C}$ with weight space $V_\lambda$ and $w \in V_\lambda$. Since $V_\lambda$ is $L$-invariant, we have that $V_\lambda$ is $z$-invariant. Since $V_\lambda$ is a complex vector space, $z \in \mathrm{gl}(V_\lambda)$ has an eigenvector. Say $v \in V_\lambda$ is an eigenvector of $z$ with eigenvalue $\alpha$. Then we show that $v$ is an eigenvector  of $L$:

For $x \in L$, we can write $x  = m + az$ for some $m \in M, a \in \mathbb{C}$. Also

$$
x(v) = m(v) + az(v) = \lambda(m)v + a\alpha v = (\lambda(m) + a \alpha)v,
$$

 which shows that $v$ is an eigenvector of $x$. Since $x$ is arbitrary, it follows that $v$ is an eigenvector of $L$.                                                        $\square$

## Theorem (Lie's theorem, requiring characteristic being zero)

Let $V$ be a vector space over $\mathbb{F} = \mathbb{C}$ and $L$ a solvable subalgebra of $\mathrm{gl}(V)$. Then there exists a basis $\mathcal{B}$ such that wrt $\mathcal{B}$ the matrix of every element of $L$ is upper triangular. That is, $L$ embeds into $\mathrm{b}_n(\mathbb{C})$.

## Corollary

Let $L$ be a solvable Lie algebra of $\mathrm{gl}(V)$ where $V$ is vector space over $\mathbb{C}$. If $x \in [L, L]$ then $x$ is nilpotent.

## Recall:

$[\mathrm{b}_n, \mathrm{b}_n] = \mathrm{u}_n$.

## Corollary

Let $L$ be a Lie algebra over $\mathbb{F} = \mathbb{C}$. Then if $L$ is solvable if and only if $[L, L]$ is nilpotent.

---

# Representations

---

# Jordan decomposition

## Lemma

Let $x  \in \mathrm{gl}(V)$. If $x = d + n$ is the Jordan decomposition then $\mathrm{ad}(x) = \mathrm{ad}(d) + \mathrm{ad}(n)$ is the J.D. of $\mathrm{ad} \in \mathrm{gl}(\mathrm{gl}(V))$.

## Proposition

Let $L$ be a subalgebra of $\mathrm{gl}(V)$. If $\mathrm{tr}(xy) = 0$ for all $x, y \in L$ then $L$ is solvable.

## Corollary

If $L$ is a Lie algebra over $\mathbb{C}$. Then $L$ is solvable if and only if $\mathrm{tr}(\mathrm{ad}(x)\circ \mathrm{ad}(y)) = 0$ for all $x \in L$ and $y \in [L, L]$.

---

# The Killing form

## Definition

$\kappa \colon L \times L \to \mathbb{C}$ such that $\kappa(x, y) = \mathrm{tr}(\mathrm{ad}(x) \circ \mathrm{ad}(y)$ for all $x, y \in L$.

## Lemma

$$
\kappa([x, y], z) = \kappa(x, [y, z]).
$$

## Lemma

Let $L$ be complex Lie algebra with ideal $I$. Then the restriction of $\kappa$ to $I$ is the Killing form on $I$. That is, $\kappa_L(x, y) = \kappa_I(x, y)$ for all $x,y \in L$.

## Theorem (Cartan's first criterion)

If $L$ is complex Lie algebra, then $L$ is solvable if and only if $\kappa(x, y) = 0$ for all $x \in L, y \in [L, L]$.

## Definition

If $\tau$ is a symmetric bilinear form, then $\tau$ is called nondegenerate if

$$
V^\perp = \{x \in V\colon \tau(x, v) = 0 \ \forall v \in V\} = 0
$$

 (and $V^\perp$ is called the radical of $\tau$).

### Recall (for a fixed basis $\mathcal{B}$)

$\tau$ is symmetric $\iff$$A:= [\tau]_{\mathcal{B}}$ is symmetric ($\iff$$A = A^T$).

$\tau$ is nondegenerate $\iff$$\det([\tau]_{\mathcal{B}}) \neq 0$

## Lemma

If $\tau$ is a nondegenerate symmetric bilinear form, then for $W \subseteq V$ we have

$$
\dim(V) = \dim(W) +\dim(W^{\perp}).
$$

Moreover, if $W \cap W^{\perp} = 0$ then $V = W \oplus W^{\perp}$, $(W^{\perp})^{\perp} = W$, and $\tau_W, \tau_{W^{\perp}}$ are nondegenerate.

## Lemma

Let $L$ be a complex Lie algebra and $I$ an ideal of $L$. Then $I^{\perp} = \{x \in L \colon \kappa(x, i) = 0 \ \forall  i \in I\}$ is an ideal of $L$.

## Theorem (Cartan's second criterion)

The complex Lie algebra $L$ is semisimple if and only if the Killing form $\kappa$ of $L$ is nondegenerate.

*Proof.* Suppose for contradiction that $\kappa$ is degenerate. Then $L^{\perp} \neq 0$.

We know that $L^{\perp}$ is an ideal of $L$. Let $x \in L^{\perp}, y \in [L^{\perp}, L^{\perp}]$, then $\kappa(x, y) = 0$ by definition of $L^{\perp}$.

Since the Killing form on $L^{\perp}$ is the restriction of the Killing form of $L$, it follows that $\kappa_{L^{\perp}}(x, y) = 0$ and Cartan's first criterion applies—$L^{\perp}$ is solvable. Hence, $L^{\perp}$ is contained in $\mathrm{Rad}(L)$ and is nontrivial. Thus $L$ is not semisimple, a contradiction.

Now assume $L$ is not semisimple, we show that $\kappa$ is degenerate. We know that $\mathrm{Rad}(L) \neq 0.$ Moreover, this implies that $L$ has a nonzero abelian ideal, say $I_0 \trianglelefteq L$. Let $i \in I_0$, $x, y \in L$, then

$$
\begin{aligned} &\mathrm{ad}(i) (\mathrm{ad}(x) (\mathrm{ad}(i)(y)))\\ = &[i, [x, [i, y]]]\\ = & 0.\end{aligned}
$$

It follows that $\mathrm{ad}(x)\mathrm{ad}(i) (\mathrm{ad}(x) (\mathrm{ad}(i)(y))) = (\mathrm{ad}(x) \mathrm{ad}(i))^2(y) = 0$. In particular, $\mathrm{ad}(x) \mathrm{ad}(i)$ is nilpotent. By Engel's theorem we know that $\mathrm{ad}(x) \mathrm{ad}(i)$ is strictly upper triangular for some basis, thus $\mathrm{tr}(\mathrm{ad}(x) \mathrm{ad}(i)) = 0$. So for all $i \in I_0$, $x \in L$ we have $\kappa(x, i) = 0$. But since $0 \neq I_0 \subseteq L^{\perp}$, this shows that $\kappa$ is degenerate.       $\square$

## Lemma

Let $L$ be a complex semisimple Lie algebra, and $I \trianglelefteq L$. Then

1. $I \cap I^{\perp} = 0$.
2. $L = I \oplus I^{\perp}$ as vector space.
3. $I$ and $I^{\perp}$ are complex semisimple Lie algebras.

    *Proof.* (2) follows (1) since by Cartan's second criterion we know that $\kappa$ is nondegenerate on $L$.

     (1). $I$ and $I^{\perp}$ are ideals, so their intersection $I \cap I^{\perp}$ is also an ideal. We claim that for $x, y \in I \cap I^{\perp}$ we have $\kappa(x, y)= 0$. To see this, recall that the restriction of $\kappa$ to $I \cap I^{\perp}$ is the same as $\kappa_{I \cap I^{\perp}}$. Thus, $\kappa _{I \cap I^{\perp}} = 0$. Cartan's first C says that $I \cap I^{\perp}$ is solvable, so $I \cap I^{\perp} \subseteq \mathrm{Rad}(L) = \{0\}.$ In particular, $I\cap I^{\perp} = 0$.

    (3) Follows from Cartan's second C.    $\square$


---

---

# Back to derivations

## Theorem (Primary Decomposition theorem)

Let $x \in \mathrm{gl}(V)$ with minimal polynomial

$$
(x - \lambda_1)^{a_1}\cdots (x - \lambda_r)^{a_r},
$$

where $\lambda_i$ are distinct eigenvalues of $x$ and $a_i \ge 1$.

---

# Cartan subalgebras

## Lemma

$x_1, \dots, x_n \in \mathrm{gl}(V)$ are simultaneously diagonalisable $\iff$ $x_1, \dots, x_n$ are diagonalisable and pairwise commute.

## Definition

Let $H$ be a subalgebra of $L$ such that

1. $H$ is abelian.
2. Every element in $H$ is semisimple. (i.e. $\mathrm{ad}(x)$ is diagonalisable for all $x \in H$.)
3. $H$ is maximal with respect to 1 & 2.

Then $H$ is called a Cartan subalgebra of $L$.

## Lemma 13.0.2

$L$, a semisimple complex Lie algebra, contains a nonzero Cartan subalgebra.

*Proof.* Let $x \in L$ and $x = d + n$ be its abstract Jordan decomposition. If $d = 0$ then $x$ is ad-nilpotent. If this is true $\forall x \in L$, then Engel's theorem says that $L$ is nilpotent, contradicting the fact that $L$ is semisimple.

Thus, there exists $x$ with $d \neq 0$ and so $0 \neq d \in L$. Let $h$ be such a semisimple, nonzero element. Then $\langle h \rangle$ is an abelian subalgebra consisting of entirely semisimple elements.  Q: What about maximality? A: Take the maximal abelian subalgebra containing only semisimple elements and $\langle h \rangle$, then it is a Cartan subalgebra as desired. $\square$

## Lemma 13.0.3

Let $y \in L$ and $A \subseteq L$ a subalgebra. Then $C_L(y), C_L(A)$ are subalgebras of $L$.

*Proof.* $C_L(y) = \ker(\mathrm{ad}(y))$ so a subspace of $L$. We now check that it is closed under the Lie bracket: let $a, b \in C_L(y)$,

$$
\begin{aligned} [y, [a, b]] = & -[b, [y, a]] - [a, [b, y]] \\= &-[b, 0] - [a, 0]\\ = &0.\end{aligned}
$$

Since $[y, a] = [b, y] = 0$. This shows that $[a, b] \in C_L(y)$. Similarly, $C_L(A)$ is a subalgebra since $C_L(A) = \cap_{x \in A} C_L(x)$.     $\square$

## Lemma 13.0.4

If $H$ is a Cartan subalgebra, and $h \in H$. Then $H \subseteq C_L(H) \subseteq C_L(h)$.

### Goal of this section: to prove that $H = C_L(H)$.

## Lemma 13.0.5

Let $H$ be a Cartan subalgebra, $h_0 \in H$ such that $\dim C_L(h_0) \le \dim C_L(h)$ for all $h \in H$. Then $C_L(h_0) = C_L(H)$.

*Proof.* Suppose $a \in Z(C_L(h_0))$ for all $a \in H$. Then $[H, C_L(h_0)] = 0$ (in other words, $C_L(h_0)$ centralises $H$) and so $C_L(h_0) \subseteq C_L(H)$. But the previous lemma gives the converse containment, the claimed result immediately follows.

We now show that $H \subseteq Z(C_L(h_0))$. For a contradiction, we assume that there exists $a \in H$ such that $a \notin Z(C_L(h_0))$. Consider the intersection $C_L(a) \cap C_L(h_0)$: choose $e_1, \dots, e_k$ a basis of this intersection; these are simultaneous eigenvectors for $a$ and $h_0$ since the elements of the intersection are diagonalisable and pairwise commute.

Extend this basis to $e_1, \dots, e_k, f_1, \dots, f_l$, basis of $C_L(a)$. These are simultaneous eigenvectors for $a$ and $h_0$.

Extend this basis to $e_1, \dots, e_k, g_1, \dots, g_r$, basis of $C_L(h_0)$. These are simultaneous eigenvectors for $a$ and $h_0$.

Extend this basis to $e_1, \dots, e_k, f_1, \dots, f_l, g_1, \dots, g_r$, basis of $C_L(a) + C_L(h_0)$. These are simultaneous eigenvectors for $a$ and $h_0$. In particular, we have

$$
\begin{aligned} &[a, e_i] = 0 = [h_0, e_i]\ \forall i \\ &[a, f_i] = 0 \neq \alpha_i f_i = [h_0, f_i] \ \forall i\\ &[a, g_i] = \beta_i g_i \neq 0 = [h_0, g_i] \ \forall i.\end{aligned}
$$

Now make last extension: let

$$
e_1, \dots, e_k, f_1, \dots, f_l, g_1, \dots, g_r, v_1, \dots, v_s
$$

be basis of $L$, where $v_1, \dots, v_s$ are simultaneous eigenvectors for $a$ and $h_0$ and

$$
[a, v_i] = \gamma_i v_i \neq 0 \neq \delta_i v_i = [h_0, v_i].
$$

Using this, let $t = a + \lambda h_0 \in H$ with $\lambda \in \mathbb{C}$ such that $\lambda \neq 0$ and $\lambda \neq \frac{-\gamma_i}{\delta_i}$ for all $1 \le i \le s$. Then

$$
\begin{aligned} ad(t)(e_i) =&[t, e_i] + [a, e_i] + \lambda[h_0, e_i] = 0.\\&[t, f_i] = [a, f_i] + \lambda[h_0, f_i] = \lambda \alpha_i f_i \neq 0.\\ &[t, g_i] = [a, g_i] + \lambda[h_0, g_i] = \beta_i, g_i] \neq 0.\\&[t, v_i] = [a, v_i] + \lambda[h_0, v_i] = (\gamma_i + \lambda\delta_i)v_i \neq 0.\end{aligned}
$$

So $e_1, \dots, f_1, \dots, g_1, \dots, v_s$ is a basis of eigenvectors for $t$ ($\mathrm{ad}(t)$). Also, $\dim C_L(t) = k < k + r = \dim C_L(h_0)$, a contradiction.      $\square$

---

# Roots of $L$ relative to a Cartan subalgebra $H$

## Decomposition $L$ using a Cartan subalgebra

Let $L$ be a semisimple complex Lie algebra. Recall that $H$ acts on $L$ via the adjoint map

$$
\mathrm{ad}(h) \colon L \to L\quad \forall h \in H.
$$

Since $H$ is abelian and consists only of semisimple elements, there exists a basis of common eigenvector for $H$ (shorthand for $\mathrm{ad}(H)$).

If $v$ is such a common e-vector, then there exists a weight $\alpha \in \mathrm{ad}(H)^* \cong H^*$ such that $L_\alpha$, the corresponding weight space, is nonzero. That is,

$$
L_\alpha = \{x \in L \colon [h, x] = \alpha(h)x \quad \forall h \in H \} \neq \{0\}.
$$

 In particular,

$$
L_0 = \{x \in L \colon [h, x] = 0 \quad \forall h \in H \} = C_L(H) \neq \{0\},
$$

as it contains $H$.

## Definition

$$
\Phi = \{\alpha \in H^* \colon \alpha \neq 0 \ \mathrm{and}\ L_\alpha \neq \{0\}\}.
$$

Call this the *set of roots* of $L$ relative to $H$; $\alpha \in \Phi$ is called a *root* of $L$; $L_\alpha$ for $\alpha \in \Phi$ is called *the root space of $L$ relative to $\alpha$.*

## Theorem

If $L$ is finite-dimensional, then $|\Phi|$ is finite and

$$
L = L_0 \oplus \bigoplus_{\alpha \in \Phi} L_\alpha.
$$

---

Recap: from now on always assume $L$ to be a semisimple complex Lie algebra; $H^*$ denotes the dual space of $H$.

## Lemma 14.2.1

For $\alpha, \beta \in H^*$, then

1. $[L_\alpha, L_\beta] \subseteq L_{\alpha + \beta}$
2. If $\alpha + \beta \neq 0$ then $\kappa(L_\alpha, L_\beta) = 0$
3. $L_0 \cap L_0^{\perp} = \{0\},$ thus $\kappa|_{L_0}$ is nondegenerate

    *Proof.* 1.  For $h \in H$, we have

    $$
    \begin{aligned} \mathrm{ad}(h) ([x, y]) &= [h, [x, y]] = -[y, [x, h]] - [x, [y, h]]\\ &= -[y, [\alpha(h)x] + [x, \beta(h)y]\\ &= \alpha(h)[x, y] + \beta(h)[x, y]\\ &= (\alpha + \beta)(h)[x, y]. \qquad \square \end{aligned}
    $$

    2. Let $\kappa$ be the Killing form on $L$. Suppose that $\alpha + \beta \neq 0$. Then for each $h \in H$,

    $$
    \begin{aligned} \alpha(h) \kappa(x, y) = & \kappa(\alpha(h)x, y) = \kappa([h, x], y)\\ =& -\kappa([x, h], y) = -\kappa(x, [h, y]) = -\kappa(x, \beta(h)y)\\ =& -\beta(h)\kappa(x, y).  \end{aligned}
    $$

    Since $\alpha + \beta \neq 0$, there exists some $h_0 \in H$ with $(\alpha + \beta)(h_0) \neq 0$, forcing $\kappa(x, y) = 0.\qquad \square$

    3. Assume that $0\neq a \in L_0 \cap L_o^{\perp}$ so $\kappa(a, t) = 0$ for all $t \in L_0$. Let $v \in L$ then $v = v_0 + \sum_{\alpha \in \Phi} v_\alpha$, where $v_0 \in L_0, v_\alpha \in L_\alpha$. So

    $$
    \begin{aligned} \kappa(a, v) & = \kappa(a, v_0 + \sum_{\alpha \in \Phi} v_\alpha)\\ & = \kappa(a, v_0) + \sum_{\alpha \in \Phi} \kappa(a, v_\alpha) \\ & = 0.\end{aligned}
    $$

    It follows that $a \in L^{\perp}$, which is a contradiction since $L$ is semisimple and $L^{\perp} = 0$. $\square$


 **

## Theorem 14.2.2

<aside>
💡 Let $L$ be a semisimple complex Lie algebra and $H$ be a Cartan subalgebra of $L$. Then $H = C_L(H)$, namely, $H$ is self-centralising.

</aside>

*Proof.*

---

## Sets of roots relative to $H$

## Lemma 14.3.1

For each $0 \neq h \in H$, there exists $\alpha \in \Phi$ with $\alpha(h_0) = 0$ for all $\alpha \in \Phi$.

*Proof.*  Suppose not. Then there exists some $\alpha \in \Phi$ such that $\alpha(h_0) = 0$ for all $\alpha \in \Phi$.

## Corollary14.3.2

The set of roots span the dual space $H^*$.

## Lemma 14.3.3

If $\alpha \in \Phi$, then $-\alpha \in \Phi$.

*Proof.* Otherwise, for all $\beta \in \Phi \cup \{0\}$, we have $\kappa(L_\alpha, L_\beta) = 0$. Thus, $L_\alpha \in L^{\perp} = \{0\}$, so $L_\alpha = \{0\}$, a contradiction.

## Lemma 14.3.4

For all $\alpha \in \Phi$, there exists $t_\alpha \in H \backslash \{0\}$ such that $\forall x \in L_\alpha$, $y \in L_{-\alpha}$,

$$
[x, y] = \kappa(x, y)t_\alpha.
$$

Moreover,

$$
\kappa(t_\alpha, h) = \alpha(h) \quad \forall h \in H.
$$

 *Proof.*

Let $x \in L_\alpha, y \in L_{-\alpha}$. Then $[x, y ] \in L_{\alpha + (-\alpha)} = L_0 = C_L(H) = H$.

In particular, $\kappa$ restricted to $H$ is nondegenerate and $\kappa|_H$ induces an isomorphism between $H$ and $H^*$,

$$
 h \mapsto \kappa|_H (h, -).
$$

Since $\alpha \in \Phi \subseteq H^*$, there exists $t_\alpha \in H \backslash \{0\}$ such that $t_\alpha \mapsto \kappa(t_\alpha, -) = \alpha(-)$.

Now,

$$
\begin{aligned} \kappa(h, [x, y]) & = \kappa([h, x], y) = \kappa(\alpha(h)x, y)\\ & = \alpha(h)\kappa(x, y) = \kappa(t_\alpha, h)\kappa(x, y)\\ & = \kappa(\kappa(x, y)t_\alpha, h)\\ & = \kappa(h, \kappa(x, y)t_\alpha). \end{aligned}
$$

So $\kappa(h, [x, y] - \kappa(x, y)t_\alpha) = 0 \ \forall h \in H$. As $h, [x, y] \in H$, $\kappa(x, y)t_\alpha \in H$ as well. Moreover, $[x, y] - \kappa(x, y)t_\alpha \in  H^{\perp}$ since  $\kappa(h, [x, y] - \kappa(x, y)t_\alpha) = 0 \ \forall h \in H$. Burt $H^{\perp} \cap H = \{0\}$, it follows that $[x, y] = \kappa(x, y)t_\alpha$.             $\square$

## Corollary 14.3.5

If $\alpha \in \Phi$, then $[L_\alpha, L_{-\alpha}] = \langle t_\alpha \rangle_{\mathbb{C}}$.

*Proof.* Lemma 14.3.4 implies that  $[L_\alpha, L_{-\alpha}] \leq \langle t_\alpha \rangle_{\mathbb{C}}$. It remains to check that $[x, y] \neq 0$ for some $x \in L_\alpha, y \in L_{-\alpha}$. Suppose such $x, y$ do not exist. Then $\kappa(x, y) = 0 \ \forall x \in L_\alpha, y \in L_{-\alpha}$ and $\kappa(L_\alpha, L_\beta) = 0$ for all $\beta \in \Phi \cup \{0\}$, thus $L_ \alpha \subseteq L^{\perp} = \{0\}$, a contradiction.          $\square$

## Definition

Fix a root $\alpha \in \Phi$ and fix $0 \neq x \in L_\alpha$, $0 \neq y \in L_{-\alpha}$. Define $M_\alpha = \langle x, y, [x, y] \rangle_{\mathbb{C}}$.

We know that $[x, y] = \lambda t_\alpha$ for $\lambda = \kappa(x, y) \neq 0$. We can check that $\dim M_\alpha = 3$ and is a subalgebra of $L$.

## Lemma 14.3.6

For $\alpha \in \Phi$, then $\alpha(t_\alpha) \neq 0$.

*Proof.* Suppose not. Then $[t_\alpha, x] = \alpha(t_\alpha)x = 0$  and $[t_\alpha, y] = \alpha(t_\alpha)y = 0$. So $t_\alpha \in Z(M_\alpha)$. It follows that $M_\alpha$ is solvable, in fact nilpotent (why? We know that this implies that $[M_\alpha, M_\alpha] \subseteq Z(M_\alpha)$)

By Lie's theorem there exists a basis of $L$ such that $\mathrm{ad}_L(M_\alpha)$ is upper triangular. Since $t_\alpha \in [M_\alpha, M_\alpha]$, we have $\mathrm{ad}(t_\alpha)$ is strictly upper triangular.

Thus $\mathrm{ad}(t_\alpha)$ is nilpotent. But $t_\alpha \in H$ so $\mathrm{ad}(t_\alpha)$ is semisimple, which forces that $t_\alpha = 0$, contradiction. $\square$

So $\alpha(t_\alpha) \neq 0$ and $\kappa(t_\alpha, t_\alpha) = \alpha(t_\alpha) \neq 0$ by Lemma 14.3.4.

Let $e_\alpha = x,\;\; h_\alpha = \frac{2}{\kappa(t_\alpha, t_\alpha)} t_\alpha,\;\;f_\alpha = \frac{2}{\kappa(t_\alpha, t_\alpha)\kappa(x,y)}y$.

Then $M_\alpha = \langle e_\alpha, h_\alpha, f_\alpha \rangle$.

We can check that $M_\alpha$ is a subalgebra of $\mathrm{sl}(\mathbb{C})$ by showing that they have the same structure constants.

## Lemma 14.3.7

For all $\alpha \in \Phi$, $M_\alpha \cong \mathrm{sl}_2(\mathbb{C})$.

## Lemma 14.3.8

If $\alpha \in \Phi$ then $t_\alpha = -t_{-\alpha}$, $h_\alpha = -h_{-\alpha}$, and $\alpha(h_\alpha) = 2$.

---

# Representation theory

## Definition of $V_d$

For $d \ge 0$, define $V_d$ to be the subspace of degree-$d$ homogenous polynomials :

Basis of $V_d$: $X^d, X^{d - 1}Y, \dots, XY^{d - 1}, Y^d$.

$\dim V_d = d + 1$.

Now make $V_d$ an $\mathrm{sl}_2{\mathbb{C}}$-module by $\phi \colon \mathrm{sl}_2(\mathbb{C})\to \mathrm{gl}(V_d)$ via



$$
\begin{aligned} & \phi(e) = X\frac{\partial}{\partial Y};\\ &\phi(f) = Y\frac{\partial}{\partial X};\\ &\phi(h) = X\frac{\partial}{\partial X} - Y\frac{\partial}{\partial Y}. \end{aligned}
$$

## Theorem 15.0.2

$V_d$ is an $\mathrm{sl}_2{\mathbb{C}}$-module.

## Theorem (Weyl's theorem)

A non-zero module for a semisimple complex Lie algebra is completely reducible.

## Lemma 15.0.3

For any two basis vectors $v_1 = X^a Y^{d-a}$and $v_2 = X^bY^{d - b}$, there exists $\ell \in \mathrm{sl}_2(\mathbb{C})$ such that $\ell \cdot v_1 = v_2$.

*Proof.* It suffices to show that we can get from

$X^d \to X^{d-1}Y \to \cdots \to Y^d$ and

$Y^d \to Y^{d - 1}X \to \cdots \to X^d$.

We have precisely that

$$
f \colon X^d \mapsto dX^{d-1}Y\\ \frac{1}{d}f \colon X^d \mapsto X^{d-1}Y\\\frac{1}{d-a}f \colon X^{d-a}Y^a \mapsto X^{d-a-a}Y^{a+1}.
$$

Similarly for $e$.

## Theorem 15.0.4

$V_d$ is irreducible.

*Proof.* Suppose $U$ is a nonzero submodule of $V_d$. Then $h \cdot u \in U$ for all $u \in U$. Since $\phi_d(h)$ is diagonalisable, $\phi_d(h)|_U$ is diagonalisable. That is, there exists an eigenvector of $\phi_d(h)$ in $U$. We also the eigenvalue of $\phi_d(h)$ on $h$ — $\phi_d(h)$ has distinct values on $V_d$, $(d, d-2, \dots, -d)$, so it has $1$-dimensional eigenspaces. Moreover, each eigenspace is spanned by $X^aY^{d-a}$ for some $a$. But Lemma 15.0.3 says that every monomial in the standard basis is in $U$.  Thus $U = V_d$.

## Lemma 15.0.5

Let $V$ be an $\mathrm{sl}_2(\mathbb{C})$-module and $v \in V$ an eigenvector for $h$ with eigenvalue $\lambda$. Then

1. Either $e \cdot v = 0$ or $e \cdot v$ is an eigenvector of $h$ with eigenvalue $\lambda+2$.
2. Either $f \cdot v = 0$ or $f \cdot v$ is an eigenvector of $h$ with eigenvalue $\lambda - 2$.

    *Proof.*

    $h\cdot(e \cdot v) = e \cdot (h \cdot v) + [h, e]\cdot v = e\cdot (\lambda v) + 2e\cdot v = (\lambda + 2)e \cdot v.$

    Similar for $f$.


## Lemma 15.0.6

$V$ contains an eigenvector $w$ of $h$ such that .

1. $e\cdot w = 0$.
2. $f^d \cdot w \neq 0$, $f^{d+1} \cdot w =0$ for some $d \ge 0$.

    *Proof.* We know that $h$ has some eigenvector on $V$ such that $h \cdot v = \lambda v$, with $v \neq 0$ over $\mathbb{C}$. Consider $v, e\cdot v, e^2 \cdot v, \dots$

    If they are all non-zero then they all have distinct eigenvalues, but this implies that there are infinitely many linearly independent vectors in $V$. Absurd. So there must exist some $k \ge 0$ such that $e^k \cdot v \neq 0$, $e^{k+1} \cdot v = 0$. Consider $w, f \cdot w, f^2 \cdot w, \dots$ Same logic gives that there exists some $d \ge 0$ such that $f^d \cdot w \neq 0$ while $f^{d+1} \cdot w = 0$. $\square$


## Theorem 15.0.7

If $V$ is an irreducible $\mathrm{sl}_2(\mathbb{C})$-module, then $V \cong V_d$ for some $d \ge 0$.

*Proof.* Let $w \in V$be as in Lemma 15.0.6 and suppose that $h \cdot w = \lambda w$.

We claim that $w, f\cdot w, \dots, f^d \cdot w$ is a basis for $V$ and $\lambda = d$.

With this claim, we see that $\psi(f^k \cdot w) = f^k \cdot X^d$ is an isomorphism of modules.

Note that $X^d, f\cdot X^d, \dots$ is a basis of $V_d$.

We now prove the claim: let $U = \langle w, f \cdot w, \dots, f^d \cdot w \rangle$, where $w, f \cdot w, \dots, f^d \cdot w$ are linearly independent (they have different eigenvalues under $h$).

By construction, $U$ is invariant under $f$ and $h$. It suffices to check that $U$ is invariant under $e$, then it is a nonzero submodule of $V$, thus $V$ since $V$ is irreducible.

We show this by induction:

Base case: $e \cdot w = 0$ by definition.

Inductive hypothesis: Suppose that $e \cdot (f^k \cdot w) \in U$ for some $k \ge 0$.

Inductive deduction: Then $e \cdot (f^{k+1} \cdot w) = e \cdot f \cdot (f^k \cdot w) = fe \cdot (f^k \cdot w) + h(f^k \cdot w) \in U$ as each summand is in $U$.

Lastly, we show that $\lambda = d$.

Consider the matrix representation of $h$ acting on $V$ with respect to the basis $w, f\cdot w, \dots, f^d \cdot w$. These are all eigenvectors for $h$, so the matrix re of $h$-action is diagonal and by 15.0.5 it is

$$
\begin{pmatrix} \lambda & 0 & 0 & 0 & \dots & 0\\ 0 &\lambda - 2 & 0 & 0 & \dots & 0\\ 0 & 0 & \lambda - 4 & 0  &\dots & 0 \\ \vdots & \ddots &\ddots & \ddots & \ddots & \vdots \\ 0 & \dots & \dots & \dots & \dots & \lambda - 2d\end{pmatrix}.
$$

$\mathrm{tr}([h]) = (d + 1)(\lambda - d)$.

But $[e, f] = h$, so the matrix rep of $h$ is a commutator of matrices, which is traceless. That is, $\lambda = d$.   $\square$

---

# The importance of sl_2(C) for semisimple complex Lie algebras

Throughout this chapter $L$ is a semisimple complex Lie algebra, $H$ is a Cartan subalgebra of $L$ and $\Phi$ is the set of roots of $L$ relative to $H$. Recall that

$$
L = H \oplus \bigoplus_{\alpha \in \Phi} L_\alpha,\\M_\alpha = \langle e_\alpha, h_\alpha, f_\alpha \rangle \cong \mathrm{sl}_2(\mathbb{C})
$$

 for each root $\alpha \in \Phi$.

We know that $L$ is an $L$-module under the adjoint action ($x \cdot y = [x, y] = \mathrm{ad}_x(y)$ for all $x, y \in L$). Since $M_\alpha$ is a subalgebra, we can study $L$ as an $M_\alpha$-module.

Note that a subspace $V$ of $L$ is an $M_\alpha$-module if $V$ is invariant under the action of $M_\alpha$.

## Lemma 16.0.1

If $V$ is an $M_\alpha$-module of $L$, then the eigenvectors of $h_\alpha$ acting on $V$ are integers.

*Proof.*  Weyl's theorem says that $V$ is a direct sum of direct $\mathrm{sl}_2(\mathbb{C})$-modules, and we know that $h_\alpha$ acts with integer eigenvalues on $V_d$ for all $d \ge 0$. But Theorem 15.0.7 implies that $V \cong V_d$.    $\square$

What we know: $\alpha(h_\alpha) = 2$; if $c\alpha$ is a root, then $c\alpha(h_\alpha) = 2c$; eigenvalues of $V_d$ are $d, d-2, d-4, \dots, -d$.

## Proposition 16.0.2

For each $\alpha \in \Phi$, if $c\alpha \in \Phi$ then $c = \pm 1$.

*Proof.* Consider $U_\alpha = \langle H, L_{c\alpha} \mid c\alpha \in \Phi \rangle \subseteq L$. We know that $M_\alpha \subseteq U_\alpha$ and want to check that $U_\alpha$ is an $M_\alpha$-submodule of $L$. That is, $U_\alpha$ is invariant under the action of $M_\alpha$.

Let $h \in H$. Then (check this)

$$
[h, e_\alpha] = \alpha(h)e_\alpha \in L_\alpha,\\ [h, f_\alpha] = -\alpha(h)f_\alpha \in L_{-\alpha},\\ [h, h_\alpha] = 0
$$

are all in $U_\alpha$

Let $c\alpha \in \Phi$. Then

$$
[L_{c\alpha}, e_\alpha] \subseteq L_{(c+1)\alpha}, \\ [L_{c\alpha}, f_\alpha] \subseteq L_{(c-1_\alpha},\\ [L_{c\alpha}] \subseteq L_{c\alpha}.
$$

All in $U_\alpha$. Thus $U_\alpha$ is $M_\alpha$-invariant as desired.

What can we say about this module?

1. Let $H_\alpha = \ker (\alpha)$. Then $H_\alpha$ is a trivial $M_\alpha$-submodule of $U_\alpha$. Indeed, $H_\alpha \subseteq H \subseteq U_\alpha$ and since kernels are subspaces, it suffices to check that $[M_\alpha, H_\alpha] = 0$. To check this, let $x \in M_\alpha, h \in H_\alpha$. Then $[x, h] = -[h, x] = -\alpha(h)x = 0$.
2. $M_\alpha$ is an irreducible submodule of $M_\alpha$: It is clear that it is a submodule since $[M_\alpha, M_\alpha] \subseteq M_\alpha \subseteq U_\alpha$; it is irreducible since $M_\alpha$ is a simple as a Lie algebra.

Also, $M_\alpha \cap H_\alpha \subseteq H$, and $M_\alpha \cap H = \langle h_\alpha \rangle_{\mathbb{C}}$. So $M_\alpha \cap H_\alpha = \{0\}$ as $h_\alpha$ is not in $\ker \alpha$.

As a result, $H_\alpha \oplus M_\alpha$ is a submodule of $U_\alpha$ and $H \subseteq H_\alpha \oplus M_\alpha$.

Now we can apply Weyl's theorem and there exists a submodule $W$ of $M_\alpha$ such that $U_\alpha = (H_\alpha \oplus M_\alpha) \oplus W$.

We want to show that $W= 0$ is true only if $c = \pm 1$.

Suppose for contradiction that $c \neq \pm 1$ and $V$ is an irreducible submodule of $W$. Then $V \cong V_s$ for some $s \ge 0$.

If $s$ is even the $V$ contains an $h_\alpha$-eigenvector with eigenvalue $0$. (Why? We know that eigenvalues of $V_s$ are $\{s, s-2, \dots, -s)$.) So $\alpha(v) = 0$ and $v \in H_\alpha$. But $H_\alpha \cap V_s = \{0\}$, so $H_\alpha \cap W =\{0\}$, a contradiction.

In fact, suppose $2\alpha \in \Phi$, then $h_\alpha$ has $2\alpha(h_\alpha) = 4$ as an eigenvalue. Bur all eigenvalues of $h_\alpha$ on $H_\alpha \oplus M_\alpha$ are $0$ and $\pm 2$ (Why? By construction, $H_\alpha$ is the kernel of $\alpha$, thus $h_\alpha$ on $H_\alpha$ has zero-eigenvalues; by the first box, eigenvalues of $h_\alpha$ on $M_\alpha$ are $\pm2$.) This forces that $W$ contains an irreducible submodule $V_s$ with $s$ being even, contradiction.

Lastly, suppose that $V\cong V_s$ where $s$ is odd. Then $h_\alpha$ has an eigenvector with eigenvalue $1$, and $\alpha(h_\alpha)= 2$. This implies that $\frac12 \alpha$ is a root. But $\alpha = 2(\frac12\alpha)$ is also a root, contradicting the previous paragraph.      $\square$

## Corollary 16.0.3

$U_\alpha = M_\alpha \oplus H_\alpha$ for all $\alpha \in \Phi$.

## Corollary 16.0.4

$\dim L_\alpha = 1$ for all $\alpha \in \Phi$.

*Proof.*  $\dim U_\alpha = \dim M_\alpha + \dim H_\alpha = 3 + \dim H - 1 = \dim H + 2$.

Since $U_\alpha = H \oplus L_\alpha \oplus L_{-\alpha}$, it follows that $\dim L_\alpha = 1$. $\square$

## Definition

For $\beta \in \Phi \cup \{0\}$, then we define the $\alpha$-root string through $\beta$ to be

$S = \bigoplus_c L_{\beta + c\alpha}$ where the sum is over $c \in \mathbb{C}$ such that $\beta + c\alpha \in \Phi$.

Since $[L_\alpha, L_\beta] \subseteq L_{\alpha + \beta}$, $S$ is an $M_\alpha$-submodule of $L$.

## Lemma 16.0.5

Let $\alpha, \beta \in \Phi$ with $\alpha \neq \pm \beta$. Then

1. $\beta(h_\alpha) \in \mathbb{Z}$.
2. there exist $q, r \ge 0$ integers such that $\beta + i \in \Phi \iff i \in \mathbb{Z}$ such that $-r \le i \le q$. Moreover, $r - q = \beta(h_\alpha)$.
3. $\beta - \beta(h_\alpha)\alpha \in \Phi$.

    *Proof.*  Since $\beta(h_\alpha)$ is the eigenvalue of $h_\alpha$ acting on $L_\beta$, it must be an integer by applying Weyl's theorem + classification of  irreducible $\mathrm{sl}_2(\mathbb{C})$.

    Similarly, we can understand the $h_\alpha$-eigenvalues on the $\alpha$-string through $\beta$: In particular, we know all eigenspaces of $h_\alpha$ is one-dimensional by Corollary 16.0.4 and

    $$
    (\beta + i \alpha)(h_\alpha)=\beta(h_\alpha) + 2i \in \mathbb{Z}.
    $$

    Since all eigenspaces are one-dimensional, all eigenvalues are distinct on the $\alpha$-string through $\beta$. So depending on $\beta(h_\alpha)$, all eigenvalues are either all even or odd. Weyl's theorem says that any irreducible submodule of the $\alpha$-string, denied by $S$, is isomorphic to $V_s$ for some $s \ge 0$. So if the eigenvalues of $h_\alpha$ are all even, then $s$ is even. Suppose $S$ has more than one irreducible submodules, then there exist at least two $2$-dimensional eigenspaces with eigenvalue $0$. But the eigenvalues are all distinct, so this cannot happen. Similarly, since there cannot be two eigenspaces at eigenvalue $1$, if $S$ contains an irreducible submodule $V_s$ with $s$ being odd, then $V_s$ has to also be unique. It follows that $S$ is in fact irreducible itself (for otherwise it would contain at least two irreducible submodules).

    The Classification implies that $S \cong V_d$ for some $d \ge 0$, and the eigenvalues for $h_\alpha$ are $d, d- 2, \dots, -d$.

    Equating the expression, we can define $r, q$ by

    $$
    \begin{aligned} d &= \beta(h_\alpha) + 2q (*)\\ -d &= \beta(h_\alpha) - 2r (**) \end{aligned},
    $$

    then adding $(*)$ and $(**)$ yields $0 = 2\beta(h_\alpha) + 2q - 2r \implies r - q = \beta(h_\alpha).$

     Lastly, $\beta - \beta(h_\alpha)\alpha = \beta - (r - q)\alpha$ from the equality above, which is in $\Phi$.  $\square$


## Lemma 16.0.6

 For $\alpha, \beta \in \Phi$, we have $\kappa(h_\alpha, h_\beta) \in \mathbb{Z}$ and $\kappa(t_\alpha, t_\beta) \in \mathbb{Q}$.

*Proof.* $\kappa(h_\alpha, h_\beta) = \mathrm{tr}(\mathrm{ad}(h_\alpha)\mathrm{ad}(h_\alpha)) = \sum_{\gamma \in \Phi} \gamma(h_\alpha)\gamma(h_\beta) \in \mathbb{Z},$ since $L = H \oplus \bigoplus_{\gamma \in \Phi} L_\gamma$ and both $\mathrm{ad}(h_\alpha)$ and $\mathrm{ad}(h_\beta)$ are diagonalisable + eigenvalues of $\mathrm{ad}(h_\alpha)$ are $0$ on $H$, but $\gamma(h_\alpha)$ on $L_\gamma$ (similar for $\mathrm{ad}(h_\beta)$).

On the other hand, $\kappa(t_\alpha, t_\beta) = \kappa(\frac{\kappa(t_\alpha, t_\alpha)}{2}h_\alpha, \frac{\kappa(t_\beta, t_\beta)}{2}h_\beta) = \frac14 \kappa(t_\alpha, t_\alpha) \kappa(h_\alpha, h_\beta)\quad (\dagger).$

It yields that $\kappa(t_\alpha, t_\alpha) = \frac14 \kappa(t_\alpha, t_\alpha) \kappa(t_\alpha, t_\alpha) \kappa(h_\alpha, h_\beta) \implies \kappa(t_\alpha, t_\alpha) = \frac{4}{\kappa(h_\alpha, h_\beta)} \in \mathbb{Q}.$ (as $\kappa(h_\alpha, h_\beta) \in \mathbb{Z}$.)      $\square$

---

# Roots of $L$

Recall that there exists an explicit isomorphism $H \to H^*$ by $h \mapsto \kappa(h, -)$. So for every $\alpha \in \Phi \subseteq H^*$, there exists $t_\alpha \in H$ such that $\alpha(-) = \kappa(t_\alpha, -)$.

Generalise: for $\phi \in H^*$, let $t_\phi$ be the unique element in $H$ such that $t_\phi \mapsto \kappa(t_\phi, -) = \phi(-)$.

Now define $(-, -) \colon H^* \times H^* \to \mathbb{C}$ by $(\theta, \phi) = \kappa(t_\theta, t_\phi)$ for all $\theta, \phi \in H^*$.

Since $\kappa$ is symmetric bilinear, so is $(-, -)$.

And $(\alpha, \beta) = \kappa(t_\alpha, t_\beta) \in \mathbb{Q} \ \forall \alpha, \beta \in \Phi$ (by 16.0.6).

Hence, $\beta(h_\alpha) = \kappa(t_\alpha, t_\beta) = \kappa(t_\beta, \frac{2}{\kappa(t_\alpha, t_\alpha)} t_\alpha) = \frac{2\kappa(t_\alpha, t_\alpha)}{\kappa(t_\alpha, t_\alpha)} = \frac{2(\beta, \alpha)}{\alpha, \alpha)} \in \mathbb{Z}$.

In particular, $\beta(\alpha) \in \mathbb{Z}$.

We know that $H^* = \langle \Phi \rangle$, so there exist $\alpha_1, \dots, \alpha_\ell \in \Phi$, forming a basis of $H^*$. Let $\beta \in \Phi$, then $\beta = c_1 \alpha_1 + \cdots + c_\ell \alpha_\ell$ for some $c_1, \dots, c_\ell$. And so

$$
(\beta, \alpha_j) = \sum_{1\ le i \le \ell}c_i(\alpha, \alpha_j) = \sum_{1 \le i \le \ell} c_i(\alpha_j, \alpha_i).
$$

$$
\begin{pmatrix} (\beta, \alpha_1) \\ (\beta, \alpha_2) \\ \vdots \\ (\beta, \alpha_\ell) \end{pmatrix} = \begin{pmatrix} (\alpha_1, \alpha_1) &\ldots &(\alpha_1, \alpha_\ell \\ (\alpha_2, \alpha_1) & \ldots & (\alpha_2, \alpha_\ell) \\ \vdots & \vdots & \vdots \\ (\alpha_\ell, \alpha_1) & \ldots &(\alpha_\ell, \alpha_\ell) \end{pmatrix} \begin{pmatrix} c_1 \\ c_2 \\ \vdots \\ c_\ell\end{pmatrix}.
$$

 Since $\kappa_h$ is nondegenerate, so this matrix (above) has nonzero determinant (with $t_{\alpha_1}, \dots, t_{\alpha_\ell}$being a basis for $H$). Thus there exist unique $c_1, \dots, c_\ell$ that satisfy this matrix equation and $c_1, \dots, c_\ell \in \mathbb{Q}$.

So $\beta = c_1 \alpha_1 + \cdots + c_\ell \alpha_\ell \in \mathbb{R}[\alpha_1, \dots, \alpha_\ell]$. Consider $E =  \mathbb{R}[\alpha_1, \dots, \alpha_\ell] \subseteq H^*$ as a real subspace. We know that $\Phi \subseteq E$ and we may restrict $(-, -)$ to $E$, giving $(-, -) \colon E \times E \to \mathbb{R}$ a symmetric bilinear form.

Let $\theta \in E$, then there exists $t_\theta \in H$ such that

$$
(\theta, \theta) = \kappa(t_\theta, t_\theta) = \mathrm{tr}(\mathrm{ad}(t_\theta)^2) \\= \sum_{\gamma \in \Phi} \gamma(t_\theta)^2 = \sum_{\gamma \in \Phi} \kappa(t_\gamma, t_\theta)^2 \\= \sum_{\gamma \in \Phi}(\gamma, \theta)^2 \ \ (**).
$$

Since $(\gamma, \theta) \in \mathbb{Q} \subseteq \mathbb{R}$, $(\theta, \theta) \ge 0$ by $(**)$. And $(\theta, \theta) = 0 \iff (\gamma, \theta) = \gamma(t_\theta) = 0 \forall \gamma \in \Phi \iff \theta = 0$. So $E$ is an inner product space (Euclidean space, since finite-dimensional and real valued).

We thus have proved the following lemma.

## Lemma 16.1.1

Let $L$ be a semisimple complex Lie algebra with roots $\Phi$. Then

1. $E$ is a vector space over $\mathbb{R}$ with a real valued inner product.
2. $\langle \Phi \rangle_{\mathbb{R}} = E$ and $0 \notin \Phi$.
3. $\alpha \in \Phi \iff -\alpha \in \Phi$.
4. For $\alpha, \beta \in \Phi$, $\frac{2(\beta, \alpha)}{\alpha, \alpha)} = \kappa(t_\beta, \frac{2t_\alpha}{\kappa(t_\alpha, t_\alpha)} = \kappa(t_\beta, h_\alpha) = \beta(h_\alpha) \in \mathbb{Z}$ and $\beta - \frac{2(\beta, \alpha)}{(\alpha, \alpha)}\alpha \in \Phi$.

---

# Root systems

Let $E$ be a finite dimensional real vector space and $(-, -)\colon E \times E \to \mathbb{R}$ be an inner product, namely, a symmetric bilinear positive definite form $(x, x) \ge 0$ and $(x, x) = 0 \iff x = 0.$

For every $0\neq v \in E$ we define an orthogonal transformation $\sigma_v \colon E \to E$ the reflection in the hyperplane perpendicular to $v$: $\sigma_v(x) = x - \frac{2(x, v)}{(v, v)}v$.

Define for all $u, v \in E$: $\langle u, v\rangle = \frac{2(u, v)}{(v, v)}$. Note that $\langle -, - \rangle$ is linear in the first argument but not in the second.

## Lemma

For $x, y \in E$ we have

$$
\left(\sigma_v(x), \sigma_v(y) \right) = (x, y)\ \ \forall 0 \neq v \in E.
$$



## Definition

Let $R$ be a subset of $E$. Then $R$ is a root system if the following hold:

1. $R$ is finite, $0 \notin R$ and $\langle R \rangle_{\mathbb{R}} = E$.
2. If $\alpha \in R$, then $c \alpha \in R \iff c = \pm 1.$
3. If $\alpha \in R$, then $\sigma_\alpha (R) \subseteq R.$
4. If $\alpha, \beta \in R$, then $\langle \alpha, \beta \rangle \in \mathbb{Z}$.

Note that 3 is equivalent to saying that $\sigma_\alpha$ permutes the roots in $R$.

Key example: $L$ semisimple complex Lie algebra, $H$ a Cartan subalgebra, then $\Phi$ set of roots of $L$ relative to $H$ is a root system in $E$.

## Lemma 17.0.2

For $\alpha, \beta \in R$ with $\alpha \neq \pm \beta$,

$$
\langle \alpha, \beta \rangle  \langle \beta, \alpha \rangle \in \{0, 1, 2, 3\}.
$$

*Proof.*   By 4, $\langle \alpha, \beta \rangle, \langle \beta, \alpha \rangle \in \mathbb{Z}$. Recall that for $u, v \in E$,

$$
(u, v)^2 = (u, u)(v, v)\cos^2\theta,
$$

where $\theta$ is the angle between $u$ and $v$.

Then $\langle \alpha, \beta \rangle \langle \beta, \alpha \rangle = \frac{2(\alpha, \beta)}{(\beta, \beta)} \frac{2(\beta, \alpha)}{(\alpha, \alpha)} = \frac{4(\alpha, \beta)^2}{(\alpha, \alpha)(\beta, \beta)} = 4 \cos^2 \theta$, where $\theta$ is the angle between $\alpha$ and $\beta$. And so $\langle \alpha, \beta \rangle \langle \beta, \alpha \rangle$ is an integer between $0$ and $4$. But if $\langle \alpha, \beta \rangle \langle \beta, \alpha \rangle = 4$, then $\cos^2\theta = 1 \implies \theta = 0$ or $\pi$, then $\beta = \pm \alpha$, contradicting the assumption.

## Corollary 17.0.3

Let $\alpha, \beta \in R$. Then

1. $\langle \alpha, \beta \rangle = 0 \iff \alpha$ is perpendicular to $\beta.$
2. $\langle \alpha, \beta \rangle > 0 \iff \langle \beta, \alpha \rangle > 0.$

    *Proof.* 1 follows from 17.0.2.

    2. $\langle \alpha, \beta \rangle = \frac{2(\alpha, \beta)}{(\beta, \beta)} \ge 0 \iff \langle \alpha, \beta \rangle \ge 0$ since $(\alpha, \beta) = (\beta, \alpha)$.  $\square$


Let $\alpha, \beta \in R$. WLOG assume $(\beta, \beta) \ge (\alpha, \alpha)$.

Then $\|\langle \beta, \alpha \| = \frac{2 \|(\beta, \alpha)\|}{(\alpha, \alpha)} \ge \frac{2\|(\beta, \alpha)\|}{(\beta, \beta)} = \|\langle \alpha, \beta \rangle\|$. We can find all possible values by $\langle \alpha, \beta \rangle \langle \beta, \alpha \rangle \in \{0, 1, 2, 3\}$, and they have same sign and that $\|\langle \beta, \alpha \rangle \| \ge \|\langle \alpha, \beta \rangle \|$.

Moreover, $(\alpha, \beta) = \sqrt{(\alpha, \alpha)(\beta, \beta)}\cos\theta.$

[Roots and angles](https://www.notion.so/c9ea8bbbb55648ffa4465ed344c138ab)

## Lemma 17.0.4

For $\alpha, \beta \in R$ such that $(\beta, \beta) \ge (\alpha, \alpha)$, $\theta$ the angle between $\alpha$ and $\beta.$ Then

1. if $\pi/2 < \theta < \pi$, then $\alpha + \beta \in R$.
2. if $0 < \theta < \pi/2$, then $\alpha - \beta \in R$.

    *Proof.* By 3. $\sigma_\beta(\alpha) = \alpha - \langle \alpha, \beta \rangle \beta \in R$. If $\pi/2 < \theta < \pi$, then $\langle \alpha, \beta \rangle = -1 \implies \alpha + \beta \in R$; if $0 < \theta < \pi/2$, then $\langle \alpha, \beta \rangle = 1 \implies \alpha - \beta \in R$.  $\square$


### Example

Dimension 1: $E = \mathbb{R}$. Since $\langle R \rangle_{\mathbb{R}}$ so there exists $0 \neq \alpha \in R$. Then $-\alpha \in R$ by 2. But 2 also says that there are no other multiples of $\alpha$ in $R$. Then $R = \{\alpha, -\alpha\}$ for any $\alpha \neq 0$ (since $E$ is spanned by one root).
