---
title: Problem Set 2
parent: MIT 18.S190
nav_order: 2
math: true
toc: true
---

# Problem Set 2
{: .no_toc}

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

url: [https://ocw.mit.edu/courses/18-s190-introduction-to-metric-spaces-january-iap-2023/resources/mit18_s190iap23_pset2/](https://ocw.mit.edu/courses/18-s190-introduction-to-metric-spaces-january-iap-2023/resources/mit18_s190iap23_pset2/)

### Problem 1

> 1. Let $  x_n \to x $  and $  y_n \to y $  be two convergent sequences in $ (X, d)$ . Then, $  d(x_n, y_n) \to d(x, y) $ .
>
> 2. Let $ \{x_n\}$  and $ \{y_n\}$  be Cauchy sequences in $ X$ . Show that $ d(x_n, y_n)$  converges.
>
> Hint: show that in a metric space, $ |d(a, b) + d(a', b')| \leq d(a, a') + d(b, b')$ .
>
> *Remark 1.* You may *not* assume $ x_n$  and $ y_n$  converges in the second part of this problem. This is only true in a Cauchy complete space.

1. Let $ \epsilon>0$ , $ \exists N_1 > 0$ , for $ n \geq N_1$ , $ d(x_n, x) < \epsilon / 2$ . $ \exists N_2 >0$ , for $ n \geq N_2$ , $ d(y_n, y) < \epsilon / 2.$ 

If $ n \geq \max\{N_1, N_2\}$ , then 
 
$$ d(x_n, y_n) \leq d(x_n, x) + d(x, y) + d(y, y_n)\leq d(x, y) + \epsilon$$ 
  
$$ d(x, y) \leq d(x, x_n) + d(x_n, y_n) + d(y_n, y)\leq d(x_n, y_n) + \epsilon$$ 
 
Therefore,
$$ |d(x_n, y_n) - d(x, y)| < \epsilon \Longrightarrow d(x_n, y_n) \to d(x, y)$$ 
 
2. Claim: $ |d(a, b) - d(a', b')| < d(a, a') + d(b, b').$ 

Proof: Since $ d(a, b) \leq d(a, a') + d(a', b') + d(b, b),$  then $ d(a, b) - d(a', b') \leq d(a, a') + d(b, b).$  Also $ d(a', b') \leq d(a', a) + d(a, b) + d(b, b'),$  then $ d(a', b) - d(a, b) \leq d(a, a') + d(b, b').$  Thus, $ |d(a, b) - d(a', b')| \leq d(a, a') + d(b, b').$ 
 
Let $ \epsilon>0$ . $ \exists M_1 > 0$ , for $ n > M_1$  and $ m > M_1$ , then $ d(x_n, x_m) < \epsilon / 2$ . $ \exists M_2 > 0$ , for all $ n > M_2$ , $ m > M_2$ , then $ d(y_n, y_m) < \epsilon / 2$ .

Denote $ M := \max\{M_1, M_2\}$ , for all $ n > M, m > M$ ,

$$ |d(x_n, y_n) - d(x_m, y_m)| \leq d(x_n, y_n) + d(x_m, y_m) = \epsilon.$$ 

Thus, $ \{d(x_n, y_n)\}_{n=1}^\infty$  is a Cauchy sequence in $ \mathbb{R}$ . Since $ \mathbb{R}$  is Cauchy complete, $ \{d(x_n, y_n)\}_{n=1}^\infty$  converges.

### Problem 2

> In class, we have defined a set $  A \subset X $  to be closed if its complement is an open set in $  X $ . There is another useful definition of a closed set however. Show that $  A \subset X $  is closed if and only if every convergent sequence in $  A $  converges in $  A $ . In other words, if $  \{x_n\} $  is a convergent sequence in $  A $  such that $  x_n \to x $ , then $  x \in A $ .

We show the two definitions are equivalent.
 
(i) $  A $ 's complement is an open set in $  X $ .
 
(ii) If $  \{x_n\} $  is a convergent sequence in $  A $  such that $  x_n \to x $ , then $  x \in A $ .

(i) $ \implies$  (ii). $ \exists \varepsilon > 0, \, \text{s.t.}\, B(x,\varepsilon) = \{ y \in X : d(x,y) < \varepsilon \} \subset A$ . If $ \{x_n\}$  is a convergent sequence, let $  x := \lim_{n \to \infty} x_n $ .  Given $ \varepsilon > 0$ , $ \exists N \in \mathbb{N}$ , $ \forall n > N$ , $  d(x_n, x) < \varepsilon $ .  
 
Since $  x_n \in A $ , then $  B(x_n, \varepsilon) \subset A $ . Thus $  x \in B(x_n, \varepsilon) \subset A $ .
 
(ii) $ \implies$  (i).  Prove by contrapositive. Assume $ \forall \varepsilon > 0$ , there $ \exists y \in B(x,\varepsilon)$ , such that $  y \notin A $ , given $  x \in A $ .  Let $ \{x_n\}$  be a convergent sequence in $  A $ , such that $  x_n \to x $ . Then $ \exists N \in \mathbb{N}$ , for $  n > N $ , $  d(x_n, x) < \varepsilon /2 $ . Since $  y \in B(x, \varepsilon) $ , $  d(x,y) < \varepsilon /2 $ . Thus,  

$$ d(x_n, y) \leq d(x_n, x) + d(x, y) < \varepsilon/2 + \varepsilon/2 = \varepsilon$$ 
 
So $  x_n \to y $ . However $  y \notin A $ , which contradicts with the condition (ii).  Therefore (i) holds.

### Problem 3

> Here, we will show that $  C^0([0,1]) $  is Cauchy complete with respect to the uniform distance. Suppose that $  f_n \in C^0([0,1]) $  is a Cauchy sequence. The uniform distance on $  C^0([a,b]) $  is defined as  
>
> $$ 
> d(f,g) = \max_{x \in [a,b]} |f(x) - g(x)|.
> $$ 
> 
> (a) Fix an arbitrary $  x_0 \in [0,1] $ . Show that $  \lim_{n \to \infty} f_n(x_0) $  exists.  
> *Hint:* $  \mathbb{R} $  is Cauchy complete.

Fix any $  x_0 \in [0,1] $ . Then for $  m,n \in \mathbb{N} $ ,  
$$ 
|f_n(x_0) - f_m(x_0)| \le \max_{x\in[0,1]} |f_n(x) - f_m(x)|.
$$   

Thus $  (f_n(x_0)) $  is a Cauchy sequence in $  \mathbb{R} $ . Since $  \mathbb{R} $  is complete, the limit  $ \lim_{n\to\infty} f_n(x_0)$  exists for each $  x_0 \in [0,1] $ .

> (b) Define $  f : [0,1] \to \mathbb{R} $  by  
> $$ 
> f(x) = \lim_{n \to \infty} f_n(x).
> $$   
> Show that for all $  \varepsilon > 0 $ , there exists $  N \in \mathbb{N} $  such that  
> $$ 
> |f_n(x) - f(x)| \le \varepsilon
> $$   
> for all $  x \in [0,1] $  and for all $  n \ge N $ .

Define a function $  f:[0,1]\to \mathbb{R} $  by  

$$ f(x) := \lim_{n\to\infty} f_n(x) \quad \text{for all } x \in [0,1].$$   
 
We claim that for every $  \varepsilon>0 $  there exists $  N\in\mathbb{N} $  such that for all $  n \ge N $ ,  

$$ 
|f_n(x) - f(x)| \le \varepsilon \quad \text{for all } x \in [0,1].
$$   
 
Indeed, since $  \{f_n\} $  is Cauchy in the uniform distance, there exists $  N $  such that for all $  m,n \ge N $ ,  

$$ \max_{x\in[0,1]} |f_n(x) - f_m(x)| < \varepsilon.$$   

Fixing $  n \ge N $  and letting $  m \to \infty $  gives  

$$ |f_n(x) - f(x)| \le \varepsilon \quad \text{for all } x \in [0,1].$$ 

> (c) Show that $  f(x) $  is continuous on $ [0,1]$ . I.e., $  f \in C^0([0,1]) $ .  
> *Hint:* To show $  f(x) $  is continuous at $  x_0 $ , consider  
> $$ 
> |f(x) - f(x_0)| \le |f(x) - f_n(x)| + |f_n(x) - f_n(x_0)| + |f_n(x_0) - f(x_0)|.
> $$ 

We now show $  f $  is continuous on $ [0,1]$ . Fix $  x_0 \in [0,1] $  and $  \varepsilon>0 $ .  From part (b), there exists $  N_1 $  such that for all $  n \ge N_1 $ ,  for all $ x\in[0,1]$ , $ |f_n(x) - f(x)| < \varepsilon/3$ .

There exists $  N_2 $  such that for all $  n \ge N_2 $ ,  $ |f_n(x_0) - f(x_0)| < \varepsilon/3$ 

Pick $  n \ge \max\{N_1,N_2\} $ . Since $  f_n\in C^0([0,1]) $ , there exists $  \delta > 0 $  such that for all $  x $  with $  |x-x_0|<\delta $ ,  $ |f_n(x) - f_n(x_0)| < \varepsilon/3$ .

Then for such $  x $ ,  
$$ 
\begin{aligned}
|f(x) - f(x_0)| 
&\le |f(x) - f_n(x)| + |f_n(x) - f_n(x_0)| + |f_n(x_0) - f(x_0)| \\
&< \varepsilon/3 + \varepsilon/3 + \varepsilon/3 = \varepsilon.
\end{aligned}
$$   

Thus $  f $  is continuous at $  x_0 $ . Since $  x_0 $  was arbitrary, $  f \in C^0([0,1]) $ .

> (d) Using parts (a)–(c), explain why $  \lim_{n \to \infty} f_n = f $  as a sequence in $  C^0([0,1]) $ .

Finally, we show $  f_n \to f $  in the uniform distance. Let $  \varepsilon>0 $ . Since $  (f_n) $  is Cauchy in the uniform distance, there exists $  N $  such that for all $  m,n \ge N $ ,  
$$ 
\max_{x\in[0,1]} |f_n(x) - f_m(x)| < \varepsilon.
$$   

Fix $  n \ge N $ . Then for all $  x \in [0,1] $ ,  
$$ 
|f_n(x) - f(x)| = \lim_{m\to\infty} |f_n(x) - f_m(x)| \le \varepsilon.
$$   

Thus  $ d(f_n(x),f(x))=\max_{x\in[0,1]} |f_n(x) - f(x)| \le \varepsilon$ . Hence $  f_n \to f $ .


### Problem 4

Let $  \|\cdot\| $  be a norm on a vector space $  V $ , and let $  d(x,y) = \|x-y\| $  for all $  x, y \in V $ . Show the following three properties:

(a) $  d(\lambda x, \lambda y) = |\lambda| d(x,y) $  for all $  \lambda \in \mathbb{R} $ , and for all $  x,y \in V $ .

(b) Translation invariance: $  d(x+z, y+z) = d(x,y) $  for all $  x,y,z \in V $ .

(c) Prove $  d $  is a metric on $  V $ . This metric is called the *metric induced by the norm*.

> (a)
> $$ 
d(\lambda x, \lambda y) = \|\lambda x - \lambda y\| = \|\lambda (x-y)\| = |\lambda| \|x-y\| = |\lambda| d(x,y)
$$ 
>
> (b)  
> $$ 
d(x+z, y+z) = \|(x+z) - (y+z)\| = \|x-y\| = d(x,y)
$$ 
> 
> (c) (i) Positive definite:  $ d(x,y) \ge 0.$  If $  x=y $ , then $  x-y=0 $ , so $  d(x,y)=0 $ .  If $  d(x,y)=0 $ , then $  \|x-y\|=0 $ , hence $  x=y $ .  
>
> (ii) Symmetry:  $ d(x,y) = \|x-y\| = \|y-x\| = d(y,x)$ 
>
> (iii) Triangle inequality:
> $$ 
> d(x,z) = \|x-z\| \le \|x-y\| + \|y-z\| = d(x,y) + d(y,z)
> $$ 

### Problem 5

Let $  U $  be an open set in the metric space $  (X,d) $ . Show that $  U $  can be written as a union of arbitrarily many open balls.

> Let $  U \subseteq X $  be open. $ \forall x \in U$ , $ \exists \varepsilon_x > 0$  such that the open ball  
> $$ 
B(x,\varepsilon_x) := \{ y \in X : d(x,y) < \varepsilon_x \}
$$ 
> 
> satisfies $  B(x,\varepsilon_x) \subseteq U $ .
> 
> Claim:
> $$ 
U = \bigcup_{x \in U} B(x,\varepsilon_x)
$$ 
> Pf: $ (\subseteq)$  Let $  z \in U $ . By openness, there is some $ \varepsilon_z > 0$  such that $  B(z,\varepsilon_z) \subseteq U $ .  In particular, $  z \in B(z,\varepsilon_z) \subseteq \bigcup_{x \in U} B(x,\varepsilon_x) $ .
> 
> $ (\supseteq)$  Conversely, if $  z \in B(x,\varepsilon_x) $  for some $  x \in U $ , then by construction $  B(x,\varepsilon_x) \subseteq U $ . Hence, $  z \in U $ .
