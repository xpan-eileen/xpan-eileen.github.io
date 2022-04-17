---
layout: article
title: Permutation groups notes
tags: notes
aside:
  toc: true
mathjax: true
---

# Permutation group
    

---

## Wreath product

### Definition

Let $\Gamma$ be a set, and write $\mathrm{Fun}(\Gamma, H) = \{f : \Gamma \to H\}$, that is, the set of all functions from $\Gamma$ to a group $H$. We see that $\mathrm{Fun}(\Gamma, H)$ forms a group under the pointwise product given by

$$
⁍
$$

If $\Gamma = \{1, 2, \dots, k\}$, then $\mathrm{Fun}(\Gamma, H) \cong H^k$ with $f \mapsto (f(1), f(2), \dots, f(k))$ the isomorphism. Let $G$ be a group acting on $\Gamma$, then $G$ acts on $\mathrm{Fun}(\Gamma, H)$ via

$$
f^x(\gamma) = f(\gamma^x),\ \forall f \in \mathrm{Fun}(\Gamma, H), x \in G, \gamma \in \Gamma.
$$

We can now define the wreath product 

$$
H \wr_{\Gamma} G = G \ltimes \mathrm{Fun}(\Gamma, H),
$$

where we call $G$ the top group and $\mathrm{Fun}(\Gamma, H)$ the base group. 

Remark: 

If $G$ is a permutation group and $G \le \mathrm{Sym}(\Gamma)$, then we write $H \wr G$. In particular, if $\Gamma = \{1, 2, \dots, k\}$ then $H \wr_\Gamma G \cong G \ltimes H^k$.

## Definition

Product action:

Let $H \le \mathrm{Sym}(\Delta), G \le \mathrm{Sym}(\Gamma), \Omega = \{\phi \colon \Gamma \to \Delta\} = \mathrm{Fun}(\Gamma, \Delta)$. Then $H \wr G$ acts on $\Omega$ via *the product action*

$$
\begin{aligned} \phi^f (\gamma) = & [\phi(\gamma)]^{f(\gamma)}\ \ &\forall f \in \mathrm{Fun}(\Gamma, H)\\ \phi^x(\gamma) = & \phi(\gamma^{x^{-1}}\ \ &\forall x \ \in G.\end{aligned}
$$

Note that if 

$\Gamma = \{1, 2, \dots, k\}$, then 

- $\Omega = \Delta^k$, and
- $(\delta_1, \dots, \delta_k)^{(h_1, \dots, h_k)} = (\delta_1^{h_1}, \dots, \delta_k^{h_k})$,
- $(\delta_1, \dots, \delta_k)^x = (\delta_{1^{x^{-1}}}, \dots, \delta_{k^{x^{-1}}})$.

---

## Definition

**Frobenius group:** $G \le \mathrm{Sym}(\Omega)$ is a Frobenius group if $G$ is transitive but not regular, and $G_{\alpha, \beta} = G_\alpha \cap G_\beta = 1$ for all $\alpha, \beta \in \Omega$ with $\alpha \neq \beta$.

## Theorem

If $G$ is finite Frobenius group on $\Omega$ and let $N = \{1\} \cup \{g \in G : \mathrm{Fix}_\Omega(g) \}$, then $N$ is normal in $G$ and regular on $\Omega$. 

### Recall:

Regular subgroup $N \triangleleft G \implies G = G_\alpha \ltimes N.$ 

We call such $N$ the Frobenius kernel, and $G_\alpha$ a Frobenius complement.

## Theorem (Thompson, 1959)

A finite Frobenius kernel is nilpotent. Any sharply 2-transitive group is Frobenius.

### Recall:

$(F, +, \times)$ is a *nearfield* if commutativity condition and left-distributivity condition are  relaxed.

## Theorem

If $F$ is a nearfield, then the group 

$$
G = \{f \colon F \to F, x \mapsto xa + b \mid a \in F^*, b \in F\}
$$

is sharply 2-transitive. (Note that if $F$ is a field then $G  = \mathrm{AGL}(F)$.

Any finit sharply 2-transitive group if of this form.

*Proof (sketch).* Such a group if Frobenius and so it has a regular normal subgroup $N$.  Can build a nearfield whose additive group is $N$ and multiplicative group $G_\alpha$ by identifying $\Omega$ with $N$ and $\Omega \backslash \{\alpha\}$ with $G_\alpha$.

Remark

Zassenhaus (1936) classified the finite nearfield. Sever—Teut (2014) showed that there exists an infinite sharply 2-transitive group without a regular normal subgroup. 

## Theorem (Jordan)

Let $k > 1$, $G$ be a $k$-transitive group other than $S_k$. Then a nontrivial normal subgroup $N$ of $G$ is $(k - 1)$-transitive, excepts possibly when $k = 3$, in which case we may have that $N$ is a elementary abelian $2$-group acting regularly. 

Remark

Minimal normal subgroups play an important role in the classification of primitive groups.

## Theorem (Burnside)

Let $N \triangleleft_{\mathrm{min}} G$ of a finite 2-transitive permutation group $G$. Then either $N$ is elementary abelian and regular, or simple and primitive. 

*Proof. See Thm 4.3 of Cameron.*

How does Burnside imply Jordan?

Note: 

1. If $N \cong C_p^d$ then $G \le \mathrm{AGL}_d(p)$ acting on $p^d$ points and so it is at most $4$-transitive.
2. If $N$ is a nonabelian simple group then there is only one example where $N$ is 2-transitive: $G = \mathrm{P\Gamma L}_2(8)$ acting on 28 points and it has a normal subgroup $N = \mathrm{PSL}_2(8)$ of index 3 that is not 2-transitive. (What is $\mathrm{P\Gamma L}$?)
3. Burnside‘s result is not true when $G$ is infinite: Let $T$ be a nonabelian simple group, then $G = T \times T$ acts on $T$ by $x^{(t_1, t_2)} = t_1^{-1} x t_2$.  Under this action, the stabiliser of $1_G$ is $G_1 = \{(t, t) \mid t \in T\}$ acts on $T \backslash \{1\}$ by conjugation—the orbits are the conjugacy classes. Now, if $G$ is 2-transitive, then $G$ acts on $T$ transitively, which implies that all elements of $T$ are conjugate. In finite case, this is impossible, but if $G$ is infinite, then there exists an infinite simple group $T$ with only 1 nontrivial conjugacy class and in this case $G$ is 2-transitive. 

How to classify all the finite 2-transitive groups?

## Theorem

If $G$ is a finite 6-transitive permutation group acting on $n$ points then $G = S_n$ for $n \ge 6$ or $G = \mathrm{Alt}_n$ for $n \ge 8$. The only 5-transitiv groups are $\mathrm{Sym}_n$ with $n \ge 5$, $\mathrm{Alt}_n$ with $n \ge 7$, $\mathrm{M}_{12}$ on 12 points and $\mathrm{M}_{24}$ on 24 point. 

*Proof. (Idea)* Uses classification of finite simple groups and the classification of all the 2-transitive groups. 

Wielandt (1960) If the Schreier conjecture is true, then the only 8-transitive groups on $n$ points are $\mathrm{Alt}_n$ or $\mathrm{Sym}_n$.

Schreier conjecture: Outer automorphism group of a finite nonabelian simple group is solvable. (TRUE by CFSG). *Issue: still lacking a more fundamental (whatever it means) proof without invoking CFSG.*

For any $k$ there is an infinite $k$-transitive permutation group that is not $(k + 1)$-transitive (Hypergraph??). 

---

# The O'Nan—Scott theorem

## Setup:

Let $T$ be a nonabelian finite simple group, $k \ge 2$ and $N = T^k$. Let $D = \{(t, t, \dots, t) \mid t \in T\} \le N$ be a diagonal subgroup.

Let $\Omega$ be the set of cosets of $D$ in $N$, then $|\Omega| = |T|^{k - 1}$. As usual, $N$ acts on $\Omega$ via coset multiplication. First note that  $N$ acts faithfully: since a point-stabiliser is contained in $D$, it follows that the kernel of the $N$-action is normal in $D$ (and normal in $N$). Since $D$ is simple as it is isomorphic to $T$, the kernel of $N$-action is either trivial or the entire $D$. However, it can‘t be $D$ as $D$ is not normal in $N$. Hence $N \le \mathrm{Sym}(\Omega)$. 

Note that 

$$
D(t_0, t_1, \dots, t_{t-1}) = D(t_0^{-1}, \dots, t_0^{-1})(1, t_0t_1,\dots, t_0t_{k-1}) = D (1, t_0t_1,\dots, t_0t_{k-1}).
$$

We denote the coset $D(1, t_1, t_2 \dots, t_{k-1})$ by $[t_1, t_2, \dots, t_{k-1}]$.  And we have the action by

$$
[t_1, t_2, \dots, t_{k-1}]^{(s_0, s_1, \dots, s_{k-1})} = [s_0^{(-1)}t_1s_o, s_o^{(-1)}t_2s_2, \dots, s_0^{(-1)}t_{k-1}s_{k-1}].
$$

If $k = 2$, $\Omega = \{[t] \mid t \in T\}$ and $[t]^{(s_0, s_1)} = [s_0^{(-1)} t s_1]$.

1. $\mathrm{Aut}(T)$ also acts faithfully  on $\Omega$ by  

$$
\left(D(1, t_1, \dots, t_{k-1})\right)^\tau = D(1, t_1^\tau, \dots, t_{k-1}^\tau)\ \ \forall \tau\  \mathrm{in}\  \mathrm{Aut}(T). 
$$

Hence, $\mathrm{Aut}(T) \le \mathrm{Sym}(\Omega)$. 

2.  $\mathrm{Aut}(T)$ normalises $N$ in $\mathrm{Sym}(\Omega)$:  

$$
[t_1, t_2, \dots, t_{k-1}]^{\tau^{(-1)}(s_0, s_1, \dots, s_{k-1})\tau} = [t_1, t_2, \dots, t_{k-1}]^{(s_0^\tau, s_1^\tau, \dots, s_{k-1}^\tau)}.
$$

Hence, $\tau^{(-1)}(s_0, s_1, \dots, s_{k-1})\tau = (s_0^\tau, s_1^\tau, \dots, s_{k-1}^\tau) \in N$. 

** can‘t construct the semidirect product of $N$ by $\mathrm{Aut}(T)$ since we don‘t know if they intersect trivially in $\mathrm{Sym}(\Omega)$. For instance, the element $(s, s, \dots, s) \in N$ induces the same permutation of $\Omega$ as $i_s \in \mathrm{Inn}(T)$. That is, $\mathrm{Aut}(T) \cap N = \{(s, s, \dots, s) \mid s \in T\} \cong T \cong \mathrm{Inn}(T)$. (Recall that for a simple group $T$ we have that $\mathrm{Inn}(T) \cong T$.) Thus, 

$$
N.\mathrm{Out}(T) \cong X = \langle N, \mathrm{Aut}(T) \rangle \le \mathrm{Sym}(\Omega),
$$

i.e. $N \triangleleft X$ and $X/N \cong \mathrm{Out}(T)$ (nonsplit extension).

3.  $\mathrm{Sym}_k$ acts faithfully on $\Omega$ by point-wise acting on the coset representatives.

Note: $\mathrm{Sym}_k$ normalises $N$ and centralises $\mathrm{Aut}(T)$. 

Thus,

$$
W := \langle N, \mathrm{Aut}(T), \mathrm{Sym}_k \rangle \cong T^k.(\mathrm{Out}(T) \times \mathrm{Sym}_k).
$$

We have $N \triangleleft W$ and $N = T_1 \times T_2 \times \cdots  \times T_k$, where $T \cong T_i = \{(1, \dots, t, 1, \dots, 1) \mid t \in T\} \triangleleft N$ where the nontrivial entry appears in the i-th position. 

$W$ acts on the set $\{T_1, \dots, T_k\}$ by conjugation, transitively. 

## Theorem

The group $W$ acts primitively on $\Omega$. Moreover, if $N \le G \le W$ then $G$ acts primitively on $\Omega$ if and only if one of the following holds:

1. $k = 2$. (Trivial sense)
2. $G$ acts primitively on $\{T_1, \dots, T_k\}$. 

*Proof.*  See Thm 4.5A of Dixon & Mortimer. For instance, what is the point-stabiliser? Well, if

$$
\alpha=\{1, 1, \dots, 1\} \in \Omega.\ \mathrm{Then}\ W_\alpha = \mathrm{Aut}(T) \times \mathrm{Sym}_k\ \mathrm{with}\ N_\alpha = D.
$$

$D$ gives $\mathrm{Inn}(T)$.

## Theorem (O'Nan—Scott) (although no paper published under the name O‘Nan)

Let $G$ be a maximal subgroup of $\mathrm{Sym}_n$. Then one of the following holds:

1. $G = \mathrm{Sym}_k \times \mathrm{Sym}_{n-k}$ with $k < n/2$ (intransitive).
2. $G = \mathrm{Sym}_a \wr \mathrm{Sym}_b$ with $n = ab \ge 2$  (Imprimitive on $ab$ points; full stabiliser ). 
3. $G = \mathrm{AGL}_d(p)$ with $p$ prime, $n = p^d, \ d \ge 1$. 
4. $G = \mathrm{Sym}_m \wr \mathrm{Sym}_n$ with $n = m^k, m, k \ge 2.$
5. $G \cong T^k. (\mathrm{Out}(T) \times \mathrm{Sym}_k)$ with $n = |T|^{k-1}, k \ge 2$, and $T$ a nonabelian simple group. (Groups of diagonal type; in fact proved in 2020, is a stabiliser of some „nice“ group with some diagonal structure.)
6. $\mathrm{Inn}(T) \le G\le \mathrm{Aut}(T)$  for some nonabelian simple group $T$ and $G$ acts primitively on $\{1, 2, \dots, n\}$. Such group us called *almost simple.* That is, a group that is isomorphic to its inner automorphism group. Eg. We have $\mathrm{M}_{24} \le \mathrm{Sym}_{24}$.

Note: 

- not all groups constructed as listed are maximal. For example, $\mathrm{Sym}_3 \wr \mathrm{Sym}_k < \mathrm{AGL}_k(3) < \mathrm{Sym}_{3^k}$. And $\mathrm{PSL}_2(7) < \mathrm{AGL}_3(2) < \mathrm{Sym}_8$.

Liebeck—Praeger—Sax (1987)  determined all exceptions. 

- Any primitive group $H$ on $n$ points is contained as a subgroup of one of the $G$ in cases 3–6.
- With the CFSG one can effectively control case 6.

---

# Structure of finite primitive groups

## Definition

Let $G$ be a finite group. The *socle* of $G$ is the subgroup generated by all the minimal normal subgroups of $G$ and is denoted by $\mathrm{soc}(G)$.

Let $G$ be a finite primitive permutation group on the set $\Omega$. Let $\alpha \in \Omega$ and $N$ be a minimal normal subgroup of $G$.

- $N$ is transitive on $\Omega$ and $N \cong T^k$ for some finite simple groupTand integer $k\ge 1$.
- We can identify $\Omega$ with $\mathrm{cos}(N \colon N_\alpha)$.
- $G = G_\alpha N = NG_\alpha$. Also, $N_\alpha = N \cap G_\alpha \triangleleft G_\alpha$.
- $C_G(N)$ is semiregular, which implies that $G_\alpha \cap C_G(N) = 1 \implies$$G_\alpha$ acts faithfully by conjugation on $N$ so is isomorphic to a subgroup of $\mathrm{Aut}(N)$ that normalises $N_\alpha$.
- If $T$ is nonabelian, then $G$ transitively permutes the simple direct factors of $N$ and the permutation group induced is the same as that induced by $G_\alpha$.
- $\mathrm{soc}(T^k) = T^k$.

## Lemma

Let $G$ be a finite group and $N$ be a minimal normal subgroup of $G$. Then $N \cong T^k$ for some finite simple group $T$ and integer $k \ge 1$.

*Proof.* Let $T \triangleleft_{\min} N$ and let $g \in G$. Then $T^g \triangleleft_{\min} N$. Moreover, we know $T \cap T^g \triangleleft N$. By minimality of $T$, we know either $T \cap T^g = 1$ or $T = T^g$. In the former case, $T^g \times T \triangleleft N$. If $T^x$ is another conjugate of $T$, then similarly, either $T^x = T$ or $T \cap T^x = 1$, moreover, we deduce that either $T^x \le T^g \times T$ or $T^x \cap (T^g \cap T) = 1$ and so $T^x \times T^g \times T \triangleleft N$. Repeating this process, we see that there exists $\{T_1, T_2, \dots, T_k\}$ of conjugates of $T$ maximal such that $L = \langle T_1, \dots, T_k \rangle = T_1 \times \cdots \times T_k \le N$. On the other hand, $L$ contains all the conjugates of $T$ under $G$, and so $L \triangleleft G$. Since $L \neq 1$ and by minimality of $N$, we have that $N \le L$. Altogether, we have that $N = L = \cong T^k$. To see that $T$ is simple, we know that any normal subgroup of $T$(characteristic in $N$) is normal in $N,$ but $T$ is minimal, thus $T$ is simple.        $\square$

In turn, let   $N = T_1 \times T_2 \times \cdots \times T_k$ where $T_i \cong T$ for some nonabelian simple group $T$. For $i = 1, 2, \dots, k$ let $\pi_i \colon N \to T_i$ be the projection homomorphism onto the i-th direct factor.

## Lemma

Let $N = T_1 \times T_2 \times \cdots \times T_k$ where $T_i \cong T$ for some nonabelian simple group $T$. 

1. If $K \triangleleft N$ and $K \cong T$ then $K = T_i$ for some $i$.
2. $\mathrm{Aut}(N) = \mathrm{Aut}(T) \wr \mathrm{Sym}_k$.
3. If $H \le N$ such that $\pi_i(H) =T_i$ for all i then there exists a partition $\mathcal{B}$ of $\{1,...,k\}$ such that $H=\prod_{B \in \mathcal{B}} T_B$ where $T_B \cong T$ and $\pi_i(T_B)=T_i$ for all $i \in B$ and $\pi_i(T_B)=1$ for all $i \notin B$. 

### Example

Let $N = T^4$, and $\mathcal{B} = \{\{1, 2\}, \{3\}, \{4\}\}$. A subgroup $T_{\{1, 2\}} = \{(t, t, 1, 1) \colon t \in T\}$ projects onto $T_1$ and $T_2$. Also there are $T_{\{3\}} = T_3 = \{(1, 1, t, 1) \colon t \in T\}$ and $T_{\{4\}} = T_4$ constructed dually. Then we have another subgroup $H = \{(t, t, s, r) \colon t, s, r \in T\} = T_{\{1, 2\}} \times T_3 \times T_4.$

## Lemma

Let $G$ be a finite primitive permutation group. Then $G$ has at most two minimal normal subgroups, and if it has two then they are isomorphic, nonabelian and regular.

*Proof.* Suppose $M, N \triangleleft_{\min} G$ are distinct. Then $M \cap N \triangleleft G$. By minimality of $M, N$, it forces the intersection to be trivial. Since $M,N$ are both normal, we have that $M, N$ centralise each other. That is, $M \le C_G(N) \triangleleft G$. Since $N$ is transitive, we know that $C_G(N)$ is semiregular. But $M$ is transitive contained in $C_G(N)$, which implies that $C_G(N)$ is in fact regular. Since a regular group has no proper transitive subgroups, it follows that $M = C_G(N)$ is regular. Since $M \cap N = 1$, it follows that $N$ is nonabelian. Similarly, $N = C_G(M)$. By the uniqueness of the centraliser, there cannot be a third minimal normal subgroup of $G$. Moreover, $M$ and $N$ act via left and right multiplications, respectively.                            $\square$

- If $G$ is primitive, and $N \triangleleft_{\min} G$, then $N = \mathrm{soc}(G)$ or $\mathrm{soc}(G) = N \times M$ where $N \cong M \cong T^k$ for some nonabelian simple group $T$.

There are five cases:

1. $N$ is abelian: $N = C_p^k$ is regular. So $G_\alpha \cap N = 1$ and $G = G_\alpha \ltimes N$. Here were can identify $\Omega$ with $N$, the additive group of a $k$-dimensional vector space $V$ over $\mathrm{GF}(p)$ and let $\alpha = 0$. Then $G=G_0 \ltimes N \le \mathrm{AGL}_k( p)$, where $N$ (identified with $V$) is the subgroup of all translations. Moreover, $G_0$ is an irreducible subgroup of $\mathrm{GL}_k( p)$. We refer to groups here as being of *HA type*.
2. $N$ not unique: In general, if $N$ is nonabelian, then $N = T^k$. Then $G$ transitively permutes the simple direct factors of $N$. So is $G_\alpha$ since $G = NG_\alpha$. We identify $\Omega$ with $N$, let $\alpha =1_N$ and if $M$ is the other minimal normal subgroup then $\mathrm{Inn}(N) \ltimes N = N \times M \triangleleft G = G_\alpha \ltimes N \le \mathrm{Hol}(N)$. (Note, the first equality follows from the fact that $T = \mathrm{Inn}(T)$ when $T$ is a simple group and $N$ is a direct product of simple groups.) When $k=1$ these are groups of. *HS type*, when $k>2$ they are of *HC type,* in which case we need $G_\alpha$ to act transitively on $k$ simple direct factors of $N$. Also, $G \le H \wr \mathrm{Sym}_k$ where $H$ is of HS type. In other words, HC type groups can be generated from HS type groups by taking wreath products.
3. $N_\alpha = 1$: Again $G = G_\alpha \ltimes N$, but $G_\alpha$ acts faithfully and transitively on the set of simple direct factors of $N$. We have $k \ge 6$. Groups here can be written as *twisted wreath products* of $T$ by $G_\alpha$($T$ normal), and are referred to as being of *TW type.* Note that the smallest simple group is isomorphic to $\mathrm{Alt}_6$ with order 60, which implies that TW type occurs only when $|\Omega| \ge 60^6$. An example is to consider $G = \mathrm{Alt}_5 \wr \mathrm{Alt}_6$, then there exists a subgroup $H \le_{\max} G$ such that $H \cong \mathrm{Alt}_6$ and $H \cap \mathrm{Alt}_5^6 = 1$. 
4. $\pi_i(N_\alpha) = T_i$ for all $i$.
    1. $N_\alpha \cong T$. Up to permutational isomorphism we may assume that $N_\alpha = \{(t, t, \dots, t) \mid t \in T\}$ and $N \le G \le W \cong T^k$. $(\mathrm{Out}(T) \times \mathrm{Sym}_k)$. Also $G_\alpha \le \mathrm{Aut}(T) \wr \mathrm{Sym}_k$, normalising $N_\alpha$. So $G_\alpha \le \{(\tau, \dots, \tau) \mid \tau \in \mathrm{Aut}(T)\} \times \mathrm{Sym}_k \cong \mathrm{Aut}(T) \times \mathrm{Sym}_k$. Here $G$ acts primitively on the set of simple direct factors of $N$ and groups are of *SD type.* 
    2. $N_\alpha \cong T^\ell$ for $\ell \ge 2$. Then there exists a partition $\mathcal{B}$ of $\{1, 2, \dots, k\}$ such that $N = \prod_{B \in \mathcal{B}} T_B$ with each $B$ of size $k/\ell$. Also, there exists a primitive group $H$ of SD type on a set $\Delta$ such that $\Omega = \Delta^\ell$ and $G \le H \wr \mathrm{Sym}_\ell$. These groups are of *CD type.* 
5. $1 \neq \pi_i(N_\alpha) \neq T_i$ for all $i$.
    1. $k = 1$. Here $T \le G \le \mathrm{Aut}(T)$ and $G_\alpha$ is a maximal subgroup of $G$. There groups are of *AS type.* 
    2. $k \ge 2$. Here there exists $1 \neq R < T$ such that $N_\alpha \cong R^k$ and there is a primitive group $H$ of AS type acting on $\Delta$ with minimal normal subgroup $T$ such that $T_\delta = R$. Moreover, $\Omega = \Delta^k$ and $G \le H \wr \mathrm{Sym}_k$. These groups are of *PA type.* 

---

# Applications of O’Nan-Scott Theorem

Prompt question: are there other primitive groups on the set $\{1, 2, \dots, n\}$?

---

# Distance-transitive graphs (another application of O’Nan-Scott Theorem)

## Definition

Let $\Gamma$ be a graph with vertex set $V$. For $v,w \in V$ define $d(v, w)$ to be the length of the shortest path between $v$ and $w$. Call $d(v, w)$ the distance.

Note:

- $\Gamma$ is connected  if and only if $d(v,w)$ exists for any $v, w \in V$.
- $d$ is a metric (satisfies the triangle inequality).

The *diameter* $\mathrm{diam}(\Gamma)$ of a connexted graph $\Gamma$ equals $\max\{d(v, w) \mid v, w \in V\}$.

- If $g \in \mathrm{Aut}(\Gamma)$ then $d(v^g, w^g) = d(v, w)$ for all $v, w, \in V$.

For $i \in 0, 1, \dots, \mathrm{diam}(\Gamma)$, let

$$
\Delta_i = \{(v, w) \mid d(v, w) = i\}.
$$

Since each $\Delta_i$ is $\mathrm{Aut}(\Gamma)$-invariant, it is a union of orbitals. And we say a connected graph $\Gamma$ is distance-transitive if $\mathrm{Aut}(\Gamma)$ acts transitively on each $\Delta_i$ with $i \le \mathrm{diam}(\Gamma)$. This is equivalent to saying that each $\Delta_i$ is an orbital of $\mathrm{Aut}(\Gamma)$.

Remark:

distance-transitive $\implies$vertex-transitive + arc-transitive.

For each $i \le \mathrm{diam}(\Gamma)$ and $v \in V$ let $\Gamma_i (v) = \{w \in V \mid d(w, v) = i\}$.

## Lemma

A graph $\Gamma$ is distance-transitive if and only if it is vertex-transitive and $\mathrm{Aut}(\Gamma)_v$ acts transitively on $\Gamma_i(v)$ for each $i \le \mathrm{diam}(\Gamma)$. That is, $\Gamma_i(v)$ are the suborbits.

## Definition

A graph $\Gamma$ is called *bipartite* if there is a partition $V = \Delta_1 \cup \Delta_2$ such that if $(v, w)$ is an edge then $v \in \Delta_1$ and $w \in \Delta_2$. The *complete bipartite graph* $K_{n, n}$ has vertex set $\{v_1, v_2, \dots, v_n\} \cup \{w_1, \dots, w_n\}$ such that $v_i \sim w_j$ for all $i, j$. We deduce that $\mathrm{Aut}(K_{n, n}) = S_2 \ltimes (\mathrm{Sym}_n \times \mathrm{Sym}_n) = \mathrm{Sym}_n \wr \mathrm{Sym}_2$, imprimitive action. If $\Gamma = K_{n, n}$ then $\Gamma$ is distance-transitive, since $\mathrm{Aut}(\Gamma)_{v_1} = \mathrm{Sym}_{n-1} \times \mathrm{Sym}_n$ and $\Gamma_i (v_1) = \{w_i\}, \Gamma_i (v_2) = \{v_2, \dots, v_n\}$.

 

## Definition

 A connected graph $\Gamma$ is called *antipodal* if for $d = \mathrm{diam}(\Gamma)$, being equal or at distance $d$ is an equivalence relation on $V$.
