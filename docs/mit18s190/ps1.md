---
title: Problem Set 1
parent: MIT 18.S190
nav_order: 1
math: true
toc: true
---

# Problem Set 1
{: .no_toc}

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---


url: [https://ocw.mit.edu/courses/18-s190-introduction-to-metric-spaces-january-iap-2023/resources/mit18_s190iap23_pset1/](https://ocw.mit.edu/courses/18-s190-introduction-to-metric-spaces-january-iap-2023/resources/mit18_s190iap23_pset1/)

### Problem 1
Consider the following map: $ d : \mathbb{R}^2 \times \mathbb{R}^2 \to [0, \infty) $ where  
$$
d(x, y) =
\begin{cases}
\Vert x - y\Vert _{\mathbb{R}^2} & x, y, 0 \text{ collinear} \\
\Vert x\Vert _{\mathbb{R}^2} + \Vert y\Vert _{\mathbb{R}^2} & \text{otherwise.}
\end{cases}
$$

Here, I use $\Vert \cdot\Vert _{\mathbb{R}^2}$ to denote the Euclidean norm/magnitude of a vector in $\mathbb{R}^2$. Show that this map is a metric on $\mathbb{R}^2$. This is called the British Railway metric. (Try to figure out why!)  
Hint: Try drawing a picture, and use the fact that $\Vert \cdot\Vert _{\mathbb{R}^2}$ is a metric.

> (i) Positive definite:
> 
> $$\Vert x - y\Vert _{\mathbb{R}^2} \ge 0, \quad \Vert x\Vert _{\mathbb{R}^2} + \Vert y\Vert _{\mathbb{R}^2} \ge 0 \implies d(x, y) \ge 0$$
>
> If $d(x, y) = 0$, then if collinear, $\Vert x - y\Vert _{\mathbb{R}^2} = 0 \implies x = y.$ Otherwise:  
>
> $$\Vert x\Vert _{\mathbb{R}^2} + \Vert y\Vert _{\mathbb{R}^2} = 0 \implies \Vert x\Vert _{\mathbb{R}^2} = \Vert y\Vert _{\mathbb{R}^2} = 0 \implies x = y$$  
>
> If $x = y$, then $d(x, y) = 0.$
> 
> (ii) Symmetry: If collinear, $\Vert x - y\Vert _{\mathbb{R}^2} = \Vert y - x\Vert _{\mathbb{R}^2}.$ Otherwise, $\Vert x\Vert _{\mathbb{R}^2} + \Vert y\Vert _{\mathbb{R}^2} = \Vert y\Vert _{\mathbb{R}^2} + \Vert x\Vert _{\mathbb{R}^2}.$
> 
> (iii) Triangle inequality:
> 
> Let $x, y, z \in \mathbb{R}^2.$ If $x, z$ are not collinear with $0$, and $x, y, 0$ are collinear, then $y, z, 0$ cannot be collinear. We conclude two cases.
> 
> (Case 1) Only one pair collinear, say $x, y, 0$:  
> 
> $$d(x, y) = \Vert x - y\Vert  \le \Vert x\Vert  + \Vert y\Vert  \le (\Vert x\Vert  + \Vert z\Vert ) + (\Vert y\Vert  + \Vert z\Vert ) = d(x, z) + d(y, z) \tag{*1}$$
> 
> $$d(x, z) = \Vert x\Vert  + \Vert z\Vert  \le \Vert x - y\Vert  + \Vert y\Vert  + \Vert z\Vert  = d(x, y) + d(y, z) \tag{*2}$$
> 
> (Case 2) No pair collinear. By $(*1)$, triangle inequality holds.

![british-railway](/img/mit18s190/pset1-1.jpg)

### Problem 2
Is $ d : C^{1}([0,1]) \times C^{1}([0,1]) \to [0,\infty) $ defined by  
$$
d(f,g) = \sup_{x \in [0,1]} \vert f'(x) - g'(x)\vert 
$$
a metric on $ C^{1}([0,1]) $? If so, prove it. If not, show what properties of a metric $d$ satisfies, and explain which properties of a metric $d$ fails.

> (i) Positive definite: $d(f,g) \ge 0$. If $f = g$, then $f'(x) = g'(x), \, x \in [0,1]$, hence $d(f,g) = 0.$  
> 
> If $d(f,g) = 0$, then $\forall x \in [0,1]$, $\vert f'(x) - g'(x)\vert  = 0 \implies f'(x) = g'(x).$  But this does not lead to $f(x) = g(x)$. A counterexample is $f(x) := g(x) + C,$ where $C$ is a constant.
> 
> (ii, iii) Symmetry and Triangle inequality both hold.
>
> Note: To make it a metric, 
> 
> $$\tilde{d}(f,g)=\sup_{x \in [0,1]} \vert f(x) - g(x)\vert +\sup_{x \in [0,1]} \vert f'(x) - g'(x)\vert $$
>
> See Example 14 in [Lecture 1](https://ocw.mit.edu/courses/18-s190-introduction-to-metric-spaces-january-iap-2023/resources/mit18_s190iap23_lec1/).

### Problem 3

Show that $ d : \mathbb{R} \times \mathbb{R} \to [0, \infty) $ where  
$$
d(x, y) = \frac{\vert x - y\vert }{1 + \vert x - y\vert }
$$
is a metric on $\mathbb{R}$.

> Positive definite and symmetry are trivial to prove.  
> 
> To prove triangle inequality, rewrite  
> 
> $$d(x, y) = 1 - \frac{1}{1 + \vert x - y\vert }.$$
> 
> Then  
> 
> $$\begin{aligned}
d(x, z) = 1 - \frac{1}{1 + \vert x - z\vert } 
&< 1 - \frac{1}{1 + \vert x - y\vert  + \vert y - z\vert } \\
&= \frac{\vert x - y\vert }{1 + \vert x - y\vert  + \vert y - z\vert } + \frac{\vert y - z\vert }{1 + \vert x - y\vert  + \vert y - z\vert } \\
&\le \frac{\vert x - y\vert }{1 + \vert x - y\vert } + \frac{\vert y - z\vert }{1 + \vert y - z\vert } \\
&= d(x, y) + d(y, z).
\end{aligned}$$

### Problem 4

Define a **semi-metric** on $X$ as a metric that satisfies symmetry, the triangle inequality, and $d(x, y) \ge 0$ for all $x, y \in X$, but doesn’t necessarily satisfy $d(x, y) = 0 \implies x = y$. Specifically, $x = y \implies d(x, y) = 0$ but the opposite implication need not be true. Show that the sum of a metric and a semi-metric on $X$ is a metric on $X$. In other words, if $d$ is a metric on $X$, and $d'$ is a semi-metric on $X$, then $d + d'$ is a metric on $X$.

> $d + d'$ satisfies symmetry, the triangle inequality, and $(d + d')(x, y) \ge 0.$  
> 
> Now show it also satisfies $(d + d')(x, y) = 0 \implies x = y.$
> 
> If $(d + d')(x, y) = 0$, suppose $x \ne y.$  Then $d(x, y) \ne 0$ since it is a metric.  To satisfy $(d + d')(x, y) = 0$, $d'(x, y) = -d(x, y) \ne 0.$  Thus $x \ne y \implies d'(x, y) \ne 0$ is equivalent to $d'(x, y) = 0 \implies x = y$,  then $d'$ is a metric instead of a semi-metric. This contradicts the assumption.  
> 
> Therefore, when $(d + d')(x, y) = 0$, $x = y.$

### Problem 5

Show that $ I_t : C^{0}([a,b]) \to C^{1}([a,b]) $ is a continuous map where  
$$
I_t(f) = \int_{a}^{t} f(x) \, dx
$$
for some $ t \in [a,b] $.

> For $ f, g \in C^{0}([a,b]) $, define  
> $$d_{C^{0}}(f,g) = \sup_{x \in [a,b]} \vert f(x) - g(x)\vert $$
> 
> For $ F, G \in C^{1}([a,b]) $, define  
> $$d_{C^{1}}(F,G) = \sup_{x \in [a,b]} \vert F(x) - G(x)\vert  + \sup_{x \in [a,b]} \vert F'(x) - G'(x)\vert $$
> 
> Let $\varepsilon > 0$. We want to find $\delta > 0$ such that if $ d_{C^{0}}(f,g) < \delta $, then  $d_{C^{1}}(I_t(f), I_t(g)) < \varepsilon$.
> 
> Denote $ F = I_t(f) $, $ G = I_t(g) $. Then  
> $$
F(x) - G(x) = \int_{a}^{x} (f(s) - g(s)) \, ds
$$
> 
> Thus,  
> $$
\vert F(x) - G(x)\vert  \le \int_{a}^{x} \vert f(s) - g(s)\vert  \, ds \le (b - a) \sup_{x \in [a,b]} \vert f(x) - g(x)\vert  = (b - a) d_{C^{0}}(f,g).
$$
> 
> Also, $\vert F'(x) - G'(x)\vert  = \vert f(x) - g(x)\vert  \le d_{C^{0}}(f,g).$ Then,  
$$
\begin{aligned}
d_{C^{1}}(I_t(f), I_t(g)) &= \sup_{x \in [a,b]} \vert F(x) - G(x)\vert  + \sup_{x \in [a,b]} \vert F'(x) - G'(x)\vert  \\
&\le (b - a) d_{C^{0}}(f,g) + d_{C^{0}}(f,g)= (b - a + 1) d_{C^{0}}(f,g)
\end{aligned}
$$
> 
> We find $\delta = \frac{\varepsilon}{b - a + 1}$, then if $ d_{C^{0}}(f,g) < \delta $,  
$$
d_{C^{1}}(I_t(f), I_t(g)) < (b - a + 1) \cdot \frac{\varepsilon}{b - a + 1} = \varepsilon.
$$
