---
title: Some Proofs
parent: MIT 18.100A
nav_order: 13
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

## Theorem 2.3.4

> Let $\{x_n\}$ be a bounded sequence. Then, there exist subsequences $\{x_{n_k}\}$ and $\{x_{m_k}\}$ such that
> $$
\lim_{k\to \infty} x_{n_k} = \limsup_{n\to \infty} x_n
$$
> 
> and
> $$
\lim_{k\to \infty} x_{m_k} = \limsup_{n\to \infty} x_n.
$$

Proof: Let $a_n = \sup\{x_k \mid k\geq n\}.$ Then, $\exists n_1 \in \mathbb{N}$ such that $a_1 -1 < x_{n_1} \leq a_1$.  Now, $\exists n_2>n_1$ such that
$$
a_{n_1+1}-\frac{1}{2} < x_{n_2} \leq a_{n_1+1}
$$

since
$$
a_{n_1+1} = \sup \{x_k \mid k\geq n_1 +1\}.
$$

Similarly, $\exists n_3>n_2$ such that
$$
a_{n_2+1}-\frac{1}{3} < x_{n_3} \leq a_{n_2+1}.
$$

Continuing in this way, we obtain a sequence of integers $n_1< n_2 < n_3< \dots$ such that
$$
a_{n_k+1} - \frac{1}{k+1} < x_{n_k} \leq a_{n_k+1}.
$$

Given $\lim_{k\to \infty} a_{n_k +1} = \limsup_{n\to \infty} x_n$, by the Squeeze Theorem,
$$
\lim_{k\to \infty} x_{n_k} = \limsup_{n\to \infty} x_n.
$$

## Bolzano-Weierstrass Theorem

> Every bounded sequence has a convergent subsequence.

Proof: This follows immediately from the previous theorem, but is so important that it itself is a theorem. 

## Lemma 3.3.1

> If $f:[a,b]\to \mathbb{R}$ is continuous then $f$ is bounded.

Proof: We prove the claim by contrapositive. Suppose $f$ is not bounded. Then for each $n\in \mathbb{N}$, there is an $x_n\in [a,b]$, such that $\vert f(x_n)\vert \ge n$. 

The sequence $$\{x_n\}_{n=1}^{\infty}$$ is bounded as $a\le x_n\le b$. By the Bolzano-Weierstrass theorem, there is a convergent sequence $$\{x_{n_i}\}_{i=1}^{\infty}$$. Let $x:=\lim_{i\to\infty}x_{n_i}$. Since $a\le x_{n_i}\le b$ for all $i$, then $a\le x\le b$. The sequence $$\{f(x_{n_i})\}_{i=1}^{\infty}$$ is not bounded as $\vert f(x_{n_i})\vert \ge n_i\ge i$. Thus, $f$ is not continuous at $x$. This contradicts the assumption, so $f$ is bounded.

*Note:* Find a sequence with a certain property, then use Bolzano-Weierstrass to make such a sequence that also converges.

## Min-Max Theorem

> Let $f:[a,b]\to \mathbb{R}$. If $f$ is continuous, then $f$ achieves an absolute maximum and absolute minimum.


Proof: We will prove this for the absolute maximum. If $f$ is continuous, then $f$ is bounded by Lemma 3.3.1. Thus, the set
$$
E = \{f(x) \mid x\in [a,b]\}
$$

is bounded above. Let $L = \sup E$. Then:
1. $L$ is an upper bound for $E$, i.e. $\forall x\in [a,b], f(x)\leq L.$

2. There exists a sequence $\{f(x_n)\}_n$ with $x_n\in [a,b]$ such that $f(x_n) \to L$ (however $$\{x_n\}$$ is need not converge).

By the Bolzano-Weierstrass theorem, there exists a subsequence $$\{x_{n_k}\}_k$$ of $$\{x_n\}$$ and $d\in [a,b]$ such that $x_{n_k}\to d$ as $k\to \infty$. Hence,

$$
f(d) = \lim_{k\to \infty} f(x_{n_k}) = \lim_{n\to \infty} f(x_n) = L
$$

by the continuity of $f$. Thus, $f$ achieves an absolute maximum at $d$.
