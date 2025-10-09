---
title: Definitions
parent: MIT 18.S190
nav_order: 4
math: true
toc: true
---

# Definitions
{: .no_toc}

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Metric Space

A metric space is a set $X$ with a metric $d:X\times X \to [0,\infty)$ such that $\forall x,y,z\in X$, we have that $d$ satisfies the following properties:

1. *Positive definite:* $d(x,y) \geq 0$ and $d(x,y) = 0 \iff x=y$.
2. *Symmetric:* $d(x,y) = d(y,x)$.
3. *Triangle Inequality:* $d(x,z) \leq d(x,y) + d(y,z)$.

## Convergent sequence

A sequence $\{x_n\}$ in a metric space $(X,d)$ *converges* to $x\in X$ if and only if $\forall \epsilon>0$ there exists an $N\in \mathbb{N}$ such that $\forall n \geq N$,
$$
d(x_n, x) \leq \epsilon.
$$

## Cauchy sequence

A sequence $\{x_n\}$ in $(X,d)$ is a *Cauchy sequence* if and only if $\forall \epsilon>0$ there exists an $N\in \mathbb{N}$ such that $\forall n,m \geq N$,
$$
d(x_n, x_m) \leq \epsilon.
$$

## Open Set

A set $A\subseteq X$ is *open* if and only if $\forall x\in A$, there exists an $\epsilon >0$ such that
$$
B(x,\epsilon) := \{y\in X \mid d(x,y) < \epsilon\} \subset A.
$$

We say that $B(x,\epsilon)$ is a ball of radius $\epsilon$ centered at $x$.

## Continuous functions

Let $X$ and $Y$ be metric spaces with metrics $d_X,d_Y$ respectively. Then, a function $f: X \supset A \to Y$ is *continuous* if and only if given $x\in A$, $\forall \epsilon >0$ there exists a $\delta >0$ such that
$$
d_X(x,y) \leq \delta \implies d_Y(f(x), f(y)) \leq \epsilon.
$$

## Bounded

A sequence $\{x_n\}$ in $(X,d)$ is *bounded* if and only if there exists a $p\in X$ and a $B\in \mathbb{R}$ such that
$$
d(x_n,p) \leq B \quad \forall n\in \mathbb{N}.
$$

Similarly, a subset $A\subseteq X$ is *bounded* if and only if there exists a $p\in X$ and a $B\in \mathbb{R}$ such that
$$
d(x,p) \leq B \quad \forall x\in A.
$$

## Vector Space

A *vector space* $V$ over a field $k$ is a set of vectors which come with addition $(+: V\times V \to V)$ and scalar multiplication $(\cdot: k\times V\to V)$ along with some classic axioms: commutativity, associativity, identity and inverse of addition, identity of multiplication, and distributivity.

## Norm

A *norm* on a vector space $V$ over the real numbers is a function $\lVert \cdot\rVert:V\to [0,\infty)$ satisfying the following three properties:

1. *Positive Definite:* $\lVert v\rVert \geq 0$ and $\lVert v\rVert = 0 \iff v = 0$.
2. *Homogeneity:* $\lVert \lambda v\rVert = \vert \lambda\vert  \lVert v\rVert$ for all $v\in V$ and $\lambda \in \mathbb{R}$.
3. *Triangle Inequality:* $\lVert x+y\rVert \leq \lVert x\rVert + \lVert y\rVert$.

A vector space with a norm on it is defined as a *normed space*.

## Compact Support

A function $f\in C^0(\mathbb{R})$ has *compact support* if $f = 0$ outside of some interval $[-n,n]$ for a finite $n.$

## Support

The *support* of a function $f\in C^0(\mathbb{R})$ is the closure of the set
$$
\{x\in \mathbb{R} \mid f(x) \neq 0\}.
$$

## Covers

Let $A\subset X$ where $X$ is a metric space. Then, $$\{U_i\}_{i\in I}$$ is an *open cover* of $A$ if $$A \subset \bigcup_{i\in I} U_i$$ and $U_i$ is open for each $i$.  

A *subcover* of an open cover is a subcollection of the sets $U_i$ that still cover $A$.  

A *finite subcover* of an open cover is a finite subcollection of the sets $U_i$ that still cover $A$.

## Compactness

Let $(X,d)$ be a metric space.  
A set $A\subset X$ is *sequentially compact* if and only if every sequence in $A$ has a convergent subsequence in $A$.  

A set $A\subset X$ is *compact* or *topologically compact* if every open cover of $A$ has a finite subcover.
