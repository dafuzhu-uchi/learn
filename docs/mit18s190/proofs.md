---
title: Some Proofs
parent: MIT 18.S190
nav_order: 5
math: true
toc: true
---

# Some Proofs
{: .no_toc}

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Lecture 2, Example 20

> Let $(X,d)$ be a metric space, and let $x\in X$. Then, for any $\epsilon>0$, $B(x,\epsilon)$ is open in $X$. In fact, this ball is sometimes referred to as an *open ball*    .

Proof: Let $y\in B(x,\epsilon)$. If $x = y$ then this is automatically true, just take $\epsilon' = \frac{\epsilon}{2}$. Suppose that $y\neq 0$, and let $r = \epsilon - d(x,y)>0$. We want to show that $B(y,r) \subset B(x,\epsilon).$ Let $z\in B(y,r).$ Then 
$$ 
d(x,z) \leq d(x,y) + d(y,z) < d(x,y) + r = \epsilon.
$$ 

Therefore, $B(y,r) \subset B(x,\epsilon)$, and thus $B(x,\epsilon)$ is an open set. 


## Lecture 2, Proposition 25

> Let $\{x_n\}$ be a sequence in $\mathbb{R}$. Then, $\{x_n\}$ is convergent (and converges to $x$) if and only if $\forall \epsilon>0$, all but finitely many terms in $\{x_n\}$ are in $(x-\epsilon, x+\epsilon)$.

Proof: Given $x_n\to x$, given $\epsilon>0$ there exists an $N$ such that for all $n\geq N$, $\vert x_n-x\vert  < \epsilon$. Therefore, for all $n\geq N$, $x_n \in (x-\epsilon, x+\epsilon)$. For the other direction, fix arbitrary $\epsilon >0$ and consider $(x-\epsilon, x+\epsilon)$. Given that all but finitely many terms in $\{x_n\}$ are in $(x-\epsilon, x+\epsilon)$, there exists an $M$ such that for all $n\geq M$, $x_n \in (x-\epsilon, x+\epsilon) = B_\epsilon(x)$. Therefore, $x_n$ is convergent.

## Lecture 2, Theorem 29

Let $(X,d_X)$ and $(Y, d_Y)$ be metric spaces. Then, $f:X\to Y$ is continuous at $c\in X$ if and only if for every sequence $\{x_n\}$ in $X$ with $x_n \to c$, we have that $f(x_n) \to f(c)$.

Proof: Suppose that $f$ is continuous at $c$. Let $\{x_n\}$ be a sequence in $X$ converging to $c$. Given $\epsilon>0$, there exists a $\delta>0$ such that $d_X(x,c) <\delta \implies d_Y(f(x),f(c))<\epsilon$. Given $x_n\to c$, there exists an $N$ such that for all $n\geq N$, $d_X(x_n, c) <\delta$. Therefore, $d_Y(f(x_n), f(c))<\epsilon$. Thus, $f(x_n) \to f(c)$.

Suppose that $f$ is not continuous at $c$. Let $\epsilon>0.$ Then, for all $n\in \mathbb{N}$, there exists an $x_n$ such that $d(x_n,c) < \frac{1}{n}$ but $d_Y(f(x_n),f(c))\geq \epsilon$. Then, $x_n\to c$ but $f(x_n)$ does not converge to $f(c).$
