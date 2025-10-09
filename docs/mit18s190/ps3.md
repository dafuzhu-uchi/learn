---
title: Problem Set 3
parent: MIT 18.S190
nav_order: 3
math: true
toc: true
---

# Problem Set 3
{: .no_toc}

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

url: [https://ocw.mit.edu/courses/18-s190-introduction-to-metric-spaces-january-iap-2023/resources/mit18_s190iap23_pset3/](https://ocw.mit.edu/courses/18-s190-introduction-to-metric-spaces-january-iap-2023/resources/mit18_s190iap23_pset3/)

### Problem 1

Let $ A$  be a closed subset of $ \mathbb{R}^n$  and let $ B$  be a compact subset of $ \mathbb{R}^n$ . Show that $ A+B$  is closed.  
Hint: Let $ \{a_n\}_n$  be a sequence in $ A+B$  such that $ a_n \to z \in \mathbb{R}^n$ . Show that $ z \in A+B$ .

> $ A+B$  is the Minkowski sum
> $$ 
  A+B := \{a+b \mid a \in A, b \in B\}
 $$ 
>
> Let $ \{c_n\}_n \subseteq A+B$ , with $ c_n \to z$ . Then $ c_n = a_n + b_n$  for some $ a_n \in A, b_n \in B$ .  
>
> Since $ B$  is compact, $ \{b_n\}$  has a subsequence $ \{b_{n_k}\} \to b \in B$ . 
> 
> Then $ a_{n_k} = c_{n_k} - b_{n_k} \to z - b =: a$ .  Since $ A$  is closed, $ a \in A$ . So $ z = a + b \in A+B$ , hence $ A+B$  is closed.

### Problem 2

Let $ (X,d)$  be a metric space and $ S \subset X$ . Then, a point $ x \in S$  is an **isolated point** if there exists an $ \varepsilon > 0$  such that $ B_\varepsilon(x)$  contains no other points of $ S$ . Show that a point $ x \in S$  is an isolated point if and only if given a sequence $ \{a_n\}$  in $ S$  converging to $ x$ , it must be the case that there exists an $ N$  such that for all $ n \geq N$ , $ a_n = x$ .

> $ (\Rightarrow)$  Suppose $ x \in S$  is an isolated point. Assume for sake of contradiction that $ \forall N > 0, \exists n > N$  such that $ a_n \neq x$ .  
>
> Since $ a_n \to x$ , $ \forall \varepsilon > 0, \exists N > 0$ , for $ n > N$ , $ d(a_n, x) < \varepsilon$ .  
> 
> Because $ a_n \neq x$ , $ \bigcup_{n > N} \{a_n\} \subset B_\varepsilon(x) \setminus \{x\}$ , contradicting $ B_\varepsilon(x) \setminus \{x\}=\varnothing$ . So $ x \in S$  is an isolated point.  
>
> $ (\Leftarrow)$  Since $ a_n \to x$ , $ \forall \varepsilon > 0, \exists N > 0$ , for all $ n > N$ , $ d(a_n, x) < \varepsilon$ .  
> 
> Exists $ N$  such that for $ n \geq N$ , $ a_n = x$ . Let $ \varepsilon = d(a_N, x)/2$  such that $ B_\varepsilon(x) = \{x\}$ , so $ x$  is an isolated point.

### Problem 3

Let $ A_1, \dots, A_k \subset X$  be compact.  

We want to show $ \bigcup_{i=1}^k A_i$  is compact.

> Let $$\{U_\alpha\}_{\alpha \in I}$$  be an open cover of $ \bigcup_{i=1}^k A_i$ . $ \forall i,\ A_i \subset \bigcup_{\alpha \in I} U_\alpha \implies \{U_\alpha\} \text{ covers } A_i.$ 
> 
> Since $ A_i$ is compact, $$\exists U_{\alpha^{(i)}_1}, \dots, U_{\alpha^{(i)}_{n_i}}$$ such that $$A_i \subset \bigcup_{j=1}^{n_i} U_{\alpha^{(i)}_j}$$. 
>
> Take the union of these finite subcovers, $$\bigcup_{i=1}^k \bigcup_{j=1}^{n_i} U_{\alpha^{(i)}_j}$$.  This set is finite and covers $$\bigcup_{i=1}^k A_i$$ . Therefore $$\bigcup_{i=1}^k A_i$$  is compact. 
