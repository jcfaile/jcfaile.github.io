---
title: 'Complex Bootcamp Exercises: Integration I'
date: 2022-07-15
permalink: /posts/2022/07/bootcamp-2022-ex-3/
tags:
  - bootcamp
  - complex analysis
---

This set of problems focuses on some fundamental theorems relating to integration (Cauchy's theorem, integral formula, zeros, singularities, and the maximum principle.) 

Resources
------
Ahlfors chapter 4.1-4.3

Problems
======

Problem 1
------
When computing the Fourier transform of the function $x\mapsto e^{-x^2}$ one arrives at the integral $$ \int_L e^{-z^2}\, dz $$ where $L = \mathbb{R} + i\xi/2$. 
Can you express this as an integral over the real axis? 
<details>
	<summary>Hint</summary>
	Consider integrating over rectangles with sides on both $L$ and $\mathbb{R}$. 
</details>

Problem 2 (Prelim August 2020)
------
Is there an entire function $f$ such that $|f(z)| \geq e^{|z|}$ for all $|z| > R >0$? Either provide an example or prove none exists. 


Problem 3 (Prelim August 2009)
------
Let $f$ be a nonconstant entire function. Assume there are two complex numbers $a_1, a_2 \ne 0$ such that $$ f(z+a_1) = f(z+a_2) = f(z).$$
Show that $a_1/a_2 \in \mathbb{Q}$. 
<details>
	<summary>Hint</summary>
	Consider the cases $a_1/a_2 \notin \mathbb{R}$ and $a_1/a_2 \in \mathbb{R}$ separately. 
</details>

Problem 4 (Prelim January 2008)
------
Suppose that $f$ is entire. Show that $$ \lim_{|z| \to \infty} |f(z)| = \infty \iff f\text{ is a polynomial.} $$
<details>
	<summary>Hint</summary>
	Examine the singularity at infinity. 
</details>

Problem 5 (Prelim August 1994)
------
Prove that all conformal self maps of $\mathbb{C}$ are affine transformations. 
<details>
	<summary>Hint</summary>
	What order can the pole at infinity be? What happens if $f'(z) = 0$ for some $z$?
</details>

Problem 6 (Prelim January 2019)
------
Assume $f$ is meromorphic on $\mathbb{C}$ and that it is bounded outside some compact set. 
Show that $f$ must be a rational function. 
<details>
	<summary>Hint</summary>
	How many poles can $f$ have? Can you define $g(z) = f(z)\prod (z-z_i)^{m_i}$ and get a corresponding bound on $g$? 
</details>

Problem 7 (Prelim August 2002)
------
Let $F$ be a finite subset of $\mathbb{C}$ and let $D = \mathbb{C}\setminus F$. 
Suppose $f$ is a non-constant analytic function on $D$. Prove that $F(D)$ is dense in $\mathbb{C}$. 
<details>
	<summary>Hint</summary>
	If $f(D)$ is not dense then we can construct $g(z) = (f(z)-z_0)^{-1}$ where $z_0 \in \mathbb{C} \setminus \overline{f(D)}$. 
</details>

Problem 8 (Prelim August 2016)
------
Let $f$ be holomorphic on a connected open neighborhood of $\mathbb{D}$. Assume that $|f(z)| = |z+1|$ for all $|z| = 1$, $f(1) = 2$, and $f$ has simple zeros at $\pm i/2$ and no other zeros in $\mathbb{D}$.
Show that these properties determine $f$ uniquely. Calculate $f(0)$.
<details>
	<summary>Hint</summary>
	Consider $g(z) = f(z)/(z+1)$. 
</details>

Problem 9 (Prelim January 2014)
------
Let $f$ be an entire function and define $M(r) =\max_{|z| = r} |f(z)|$. Show $M$ is continuous on $[0,\infty)$. 


Problem 10 (Prelim January 1997)
------
Suppose that $f$ is analytic on the disk $|z| < 2$ except for a simple pole at $z = 1$ with residue $A$. 
Show that \[ \lim_{n\to\infty} \frac{f^{(n)}(0)}{n!} = - A. \]
<details>
	<summary>Hint</summary>
	Consider $g(z) := f(z) - A/(z-1)$ and try extend it to $z = 1$. 
	What is its Taylor expansion?
</details>


Problem 11
------
Suppose that $f$ in an entire function which is bounded on the half plane $H = \\{z: \text{Re}(z) > 0\\}$. 
Additionally, there exists $y_0 \in \mathbb{R}$ such that $$ \lim_{x\to \infty} f(x+iy_0) = L. $$
Prove that for arbitrary $y \in \mathbb{R}$ we have 
$$ \lim_{x\to \infty} f(x+iy) = L. $$
<details>
	<summary>Hint</summary>
	The real and imaginary parts of $f$ are maps $\mathbb{R}^2 \to \mathbb{R}$ so you may consider applying the mean value theorem on these parts. Then you can control the real/imaginary parts of $|f(x+iy) - f(x+iy_0)|$ with $|f'(x + i\xi)|, y < \xi < y_0$. 
</details> 

Problem 12 (Prelim August 2014)
------
Suppose $f$ is meromorphic on $\mathbb{D}\setminus\\{0\\}$ having poles at $z = 1/2,1/3,1/4,\dots$ Show that for every $r > 0$ the restriction of $f$ to $0 < |z| < r$ has dense image in $\mathbb{C}$. 
<details>
	<summary>Hint</summary>
	Suppose not - then we can construct $g(z) = (f(z) - w)^{-1}$ where $w \notin f(B_r(0)\setminus\{0\})$. 
</details>
