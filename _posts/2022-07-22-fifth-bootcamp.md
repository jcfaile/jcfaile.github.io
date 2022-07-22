---
title: 'Complex Bootcamp Exercises: Products and Series'
date: 2022-07-22
permalink: /posts/2022/07/bootcamp-2022-ex-5/
tags:
  - bootcamp
  - complex analysis
---

This set of problems focuses on series and product representations of holomorphic and meromorphic functions. 

Resources
------
Ahlfors chapter 5.1 - 5.2.3 and 5.3.2

Problems
======



Problem 1 (Prelim August 2015)
-----
Let $\mu$ be Lebesgue measure on $\mathbb{D}$. Let $H \subset L^2(\mathbb{D},\mu)$ be the subset of holomorphic functions. 
Show that $H$ is a closed subset.
<details>
	<summary>Hint</summary>
	Show that for every compact subset $K \subset \mathbb{D}$ there exists a constant $C_K > 0$ depending only on $K$ such that $$ \sup_{z\in K} |f(z)| \leq C_k \lVert f|_K \rVert_{L^2}.$$
	We can relate the value of $f$ at a point to its integral via the mean value property. 
</details>

Problem 2 (Prelim January 2022)
------
Let $0 < \alpha < 1$. Show that \[ \prod_{n=1}^\infty \cos(\alpha^n z)\] defines an entire function $f$ of finite order. Determine the order and genus of $f$. 
<details>
	<summary>Hint</summary>
	It may be difficulty to directly compute the order, but recall that Hadamard's theorem states that if $f$ has genus $h$ and order $\lambda$ then $h \leq \lambda \leq h + 1$. 
</details>

Problem 3 (Prelim August 2021)
------
Let $f$ be a meromorphic function on $\mathbb{C}$ satisfying $f(z)f(-z) = 1$ for all $z\in \mathbb{C}$. 
Show that there exists an entire function $g$ such that $f(z) = g(z)/g(-z)$ for all $z\in \mathbb{C}$. 
(For simplicity you may assume that $f(0) = 1$.)
<details>
	<summary>Hint</summary>
	Note that we do not necessarily have that $f$ is rational (for instance, we could have $f(z) = e^z$.) 
	However, all meromorphic functions are quotients of two entire functions. Write their canonical products.
</details>

Problem 4 (Prelim August 2021)
------
Let $f$ be an entire function satisfying a bound $|f(z)| \leq \text{exp}(|z|^n)$ for all $z\in \mathbb{C}$, where $n$ is some positive integer. 
If $f(z) = 0$ whenever $\text{exp}(\text{exp }z) = 1$ show that $f = 0$. 
<details>
	<summary>Hint</summary>
	We have enough information to compute $f$'s order and genus.
</details>

Problem 5 (Prelim August 25)
------
Find a function $f$ holomorphic on $\mathbb{C} \setminus \mathbb{N}$ with a pole of order $n$ at $z = n$ for all positive integers $n$. 
<details>
	<summary>Hint</summary>
	Find a canonical product corresponding to the zeros of $1/f$. 
</details>

Problem 6 (Prelim August 2020)
------
Prove that \[ \frac{\pi^2}{\sin^2(\pi z)} = \sum_{n=-\infty}^\infty \frac{1}{(z-n)^2} \]
<details>
	<summary>Hint</summary>
	Apply Mittag-Leffler, try to bound the resulting entire function on a single strip $0 \leq \text{Re}(z) \leq 2\pi$.
</details>

Problem 7 (Prelim January 2013)
------
Determine the partial fraction expansion for \[ \frac{1}{\sqrt{z} \sin \sqrt{z}} \]
<details>
	<summary>Hint</summary>
	While the appearance of the square root makes it seem like you must work with branches, consider the degree of terms in the Taylor series expansion of $z\sin z$. Does it matter which branch is chosen?
</details>

Problem 8 (Prelim January 2019)
------
Prove that \[ \frac{d}{dz} \left( \frac{\pi \sin(z)}{\sin(\pi z)} \right) = \sum_{n=-\infty}^\infty \frac{(-1)^{n+1} \sin(n)}{(z-n)^2} \]
for all $z\in \mathbb{C}\setminus \mathbb{Z}$, with the sum on the right hand side converging uniformly on every compact subset of $\mathbb{C}\setminus \mathbb{Z}$. 
<details>
	<summary>Hint</summary>
	Apply Mittag-Lefler before differentiating. For the resulting entire function consider its behavior as $\text{Im}(z) \to \pm \infty$. 
</details>

Problem 9 (Prelim January 2017)
------
Determine the partial fractions expansion of \[ \frac{1}{z\sin z} \]


Problem 10 (Prelim January 2016)
------
Determine all entire functions $f$ satisfying $f(\sqrt{n}) = n$ for all positive integers and $|f(z)| \leq e^{3|z|}$ for every complex number $z$. 
<details>
	<summary>Hint</summary>
	From our our problem statement we can find the order of $z\mapsto f(z) - z^2$. 
</details>


Problem 11 (Prelim January 2014)
------
Assume $f$ is entire and of finite order. Prove that if $|f(z)| \leq 1$ for all $z$ in the boundary of the half-strip \[ S = \\{z \in \mathbb{C}: \text{Re}(z) \geq 0, |\text{Im}(z)| \leq 1 \\} \] then $|f(z)| \leq 1$ for all $z\in S$. 
<details>
	<summary>Hint</summary>
	Consider the collection on functions $f(z)e^{-\epsilon z^n}$ for an appropriate choice of $n$ and $\epsilon > 0$. 
</details>

Problem 12 (Prelim August 2017)
------
Let $D_2 \subset D_1$ be two disk in $\mathbb{C}$ with $D_1$ open and $D_2$ closed. Let $f$ be an analytic function on $D_1\setminus D_2$. Show that there exist holomorphic functions $f_1$ on $D_1$ and $f_2$ on $\mathbb{C} \setminus D_2$ such that $f = f_1 + f_2$ on $D_1\setminus D_2$. 
<details>
	<summary>Hint</summary>
	Consider the integral formula over an appropriate region to construct the $f_i$. <br> As an aside, this construction for disks with the same center is used to prove the existence of Laurent series. 
</details>
