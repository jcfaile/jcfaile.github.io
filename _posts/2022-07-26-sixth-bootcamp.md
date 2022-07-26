---
title: 'Complex Bootcamp Exercises: Normal Families'
date: 2022-07-26
permalink: /posts/2022/07/bootcamp-2022-ex-6/
tags:
  - bootcamp
  - complex analysis
---

This set of problems focuses on normal families (aka precompact sets) of functions, Picard's theorem, Jensen's formula, and other topics.

Resources
------
Ahlfors sections 5.5 and 8.3

Problems
======

Problem 1 (Ahlfors 5.5.5.3)
------
Let $f$ be an entire function and define family of functions on the annulus $r_1 < |z| < r_2$ $\mathcal{F} = \\{z\mapsto f(kz):k\in\mathbb{C}\\}$. 
Show that $\mathcal{F}$ is a normal family if and only if $f$ is a polynomial. 
<details>
	<summary>Hint</summary>
	Recall an entire function $f$ is a polynomial if and only if $|f(z)| \to \infty$ as $z \to \infty$. 
</details>


Problem 2 (Prelim August 2015)
------
Let $f$ be an entire function satisfying $f(1-z) = 1-f(z)$. Show that $f(\mathbb{C}) = \mathbb{C}.$
<details>
	<summary>Hint</summary>
	Suppose not and apply Picard to find that $f(\mathbb{C}) = \mathbb{C} \setminus \{z_0\}$. 
</details>

Problem 3 (Prelim August 2020)
------
Suppose that $f$ is analytic on $\mathbb{D}$ and satisfies $|f(z)| \leq M$ for all $z\in \mathbb{D}$. Assume further that $f$ vanishes at the points $\\{z_j\\}_{j=1}^N$ where $1 \leq N \leq \infty.$)
If $N = \infty$ and $f \ne 0$ then show that $$ \sum_{j=1}^\infty (1-|z_j|) < \infty. $$
<details>
	<summary>Hint</summary>
	Jensen's formula. 
</details>

Problem 4 (Prelim January 2022)
------
Let $U,V$ be disjoint non-empty open subset of $\mathbb{C}$. Let $\\{f_n\\}_{n=1}^\infty$ be a sequence of holomorphic functions $f_n : U \to V.$
Show that some subsequence converges locally uniformly to a holomorphic function $f$, and that $f$ is one-to-one if each $f_n$ is one-to-one. <br><i>(Remark added after the exam. An extra condition is missing: $\\{f_n(u)\\}$ is bounded for some $u\in U.$)</i>
<details>
	<summary>Hint</summary>
	Since $U$ and $V$ are disjoint we can transform the sequence into a bounded sequence. 
</details>

Problem 5 (Prelim August 2021)
------
<div>Let $\{ f_n \}_{n=1}^\infty$ be bounded holomorphic functions on $\Omega = \{z\in \mathbb{C}:|z| > 1\}$ that take values in $\Omega$. 
If the sequences $\{ f_n(k) \}_{n=1}^\infty$ converge for each integer $k > 1$ then show that $\{f_n\}_{n=1}^\infty$ converges uniformly on compact subsets of $\Omega.$</div>
<details>
	<summary>Hint</summary>
	You may need to use the sub-subsequence argument to extend beyond just convergence of subsequences. 
</details>

Problem 6 (Prelim August 2015)
------
Let $\mathcal{F}$ be the set of all entire functions $f$ with the following properties. The zeros $a_1,a_2,\dots$ of $f$ satisfy $\sum_{n} |a_n|^{-1} \leq 1$. Furthermore, $f(0) = 1$, $|f'(0)| \leq 1$, and $e^{-|z|} |f(z)| \to 0$ as $|z| \to \infty$. Show that every sequence in $\mathcal{F}$ has a subsequence converging uniformly on compact subsets of $\mathbb{C}.$
<details>
	<summary>Hint</summary>
	A function of genus zero admits the canonical representation $$ C z^m \prod_{n=1}^N \left( 1 - \frac{z}{a_i} \right). $$
</details>


Problem 7 (Prelim January 2016)
------
Let $\\{f_n\\}_{n=1}^\infty$ be a sequence of holomorphic functions defined on a domain $\Omega \subset \mathbb{C}$ and assume $f_n\to f$ pointwise on $\Omega$. 
Suppose no $f_n$ ever attains a positive real value. Show that $f$ is holomorphic on $\mathbb{\Omega}.$
<details>
	<summary>Hint</summary>
	Can you conformally map the image set $\mathbb{C} \setminus \mathbb{R}^+$ to a bounded set? 
</details>

Problem 8 (Prelim August 2012)
------
Prove that for any simply connected open subset of the complex plane, there exists an analytic function that cannot be analytically continued to a larger domain.
<details>
	<summary>Hint</summary>
	By Riemann mapping theorem we can take our domain to be $\mathbb{D}$. An extension of a function $f$ will certainly not exist if $f$ is unbounded on all neighborhoods of points on the boundary.
</details>

Problem 9 (Prelim August 2011)
------
Let $\\{f_n\\}_{n=1}^\infty$ be a sequence of of one-to-one holomorphic maps from $H = \\{z:\text{Im }z > 0\\}$ into itself.
Suppose this sequence has a non-constant pointwise limit $f:H\to H$.
Prove that $f$ is holomorphic and one-to-one. 
<details>
	<summary>Hint</summary>
	Weierstrass' theorem tells us that $f$ will be holomorphic if we can upgrade our convergence from pointwise to uniform on compact sets. <br>
	To determine the injectivity of $f$ consider the limit of the argument principle applied to $f_n(z) - w$ for fixed $w \in \mathbb{C}.$
</details>

Problem 10 (Prelim January 2007)
------
Let $\\{f_n\\}_{n=1}^\infty$ be a sequence of holomorphic functions on $\mathbb{D}$ such that for every $n$ either $\text{Re }f_n(z) > 0$ or $\text{Im }f_n(z) \ne 0$, and $f_n(0) = 1$.
Show that there is a subsequence that converges to some $f:\mathbb{D} \to \mathbb{C}$ uniformly on compact sets.
Does this hold if we drop the condition $f_n(0) = 1?$
<details>
	<summary>Hint</summary>
	Note that the range of every $f_n$ is contained in a simply connected proper subset of $\mathbb{C}$. 
	Can you find any convenient conformally equivalent regions?
</details>

Problem 11 (Prelim August 2009)
------
Let $\mathcal{F}$ be the set of all holomorphic functions $f$ on $\mathbb{D}$ such that $$ \int_\mathbb{D} |f(x + iy)|^2dx\,dy \leq 1 $$ show that $\mathcal{F}$ is a normal family.
<details>
	<summary>Hint</summary>
	Selecting any disk of radius $r < 1$ apply the mean value property to get a bound on $|f(z)|$ over this domain. To finish, look for variations of Montel's theorem or find an appropriate diagonal argument. 
</details>
