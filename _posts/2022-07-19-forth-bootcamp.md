---
title: 'Complex Bootcamp Exercises: Integration II'
date: 2022-07-19
permalink: /posts/2022/07/bootcamp-2022-ex-4/
tags:
  - bootcamp
  - complex analysis
---

This set of problems focuses on the residue theorem, argument principle, and mean value property.

Resources
------
Ahlfors section 4.4-4.6

Problems
======

Problem 1 (Prelim August 2015)
------
Let $f$ be a nonconstant meromorphic function satisfying $$f(z) = f(z+\sqrt{2}) = f(z+i\sqrt{2})$$ and assume $f$ has at most a single pole in $\mathbb{D} = \\{z: |z| < 1 \\}$. 
<ol><li>
Show that there must exist a pole in $\mathbb{D}$. 
<details>
	<summary>Hint</summary>
	If there is no pole in $\mathbb{D}$ how many poles can $f$ have elsewhere?
</details>
</li><li>
b. Show that this pole cannot be simple.
<details>
	<summary>Hint</summary>
	Try integrating along a square with side lengths $\sqrt{2}$. 
</details>
</li></ol>

Problem 1 (Prelim January 1997)
------
Suppose that $f$ is a holomorphic function on a neighborhood of $\overline{\mathbb{D}}$ and on $\partial \mathbb{D}$ $f$ satisfies $|f(z)| \leq a$ when $\text{Im}(z) \geq 0$ and $|f(z)| \leq b$ when $\text{Im}(z) \leq 0$. Show that
\[ |f(z)| \leq \left(ab\right)^{1/2} \] for all $z \in \mathbb{D}$. 
<details>
	<summary>Hint</summary>
	Consider both $f(z)$ and $f(-z)$. 
</details>


Problem 1 (Prelim August 1996)
------
Suppose $f$ is analytic on an open neighborhood of $\overline{\mathbb{D}}$ and that it is injective on $|z| = 1$. 
Show that $f$ is injective on $\mathbb{D}$. 
<details>
	<summary>Hint</summary>
	Apply the Jordan curve theorem. What can you deduce about solutions to $f(z) = w$ for arbitrary $w\in \mathbb{C}$? 
</details>

Problem 1 (Prelim January 2022)
------
Let $K$ be a compact connected subset of $\mathbb{C}$ containing $\pm i$. 
Show that there exists a holomorphic branch of $(z^2 + 1)^{1/2}$ in $\mathbb{C} \setminus K$ and determine the possible values of its integral along closed curves in $\mathbb{C} \setminus K$. 
<details>
	<summary>Hint</summary>
	Recall that a branch of $\log f$ exists for a function $f$ on a domain $U$ if and only if $\int_\gamma f'/f\,dz = 0$ for all closed curves $\gamma:S^1\to U$. 
</details>

Problem 1 (Prelim August 2020)
------
Assume $f:\mathbb{C}\setminus \overline{\mathbb{D}} \to \mathbb{D}$ is holomorphic. Prove that $|f'(2)| \leq 1/3$.
<details>
	<summary>Hint 1</summary>
	Precompose with $1/z$ to make this a map $\mathbb{D}\to \mathbb{D}$.
</details>
<details>
	<summary>Hint 2</summary>
	Use a mobius transformation on the disk that maps $1/2 \mapsto 0$. 
	Then the Schwarz inequality gives a bound on the derivative at zero. 
	This variant is called the "Schwarz-Pick" theorem. 
</details>

Problem 1 (Prelim August 2020)
------
Suppose that $f$ is analytic on $\mathbb{D}$ and satisifies $|f(z)| \leq M$ for all $z\in \mathbb{D}$. Assume further that $f$ vanishes at the points $\\{z_j\\}_{j=1}^N$ where $1 \leq N \leq \infty$. 
<ol><li> 
Prove that \[ |f(z)| \leq M \left| \prod_{j=1}^m \frac{z-z_j}{1-\overline{z_j}z} \right|\quad \forall z\in\mathbb{D} \] for any $1 \leq m \leq N$ (or if $N = \infty$ then $1 \leq m < N$. 
<details>
	<summary>Hint</summary>
	Consider the function $$ g(z) = \frac{f(z)}{\prod_{j=1}^m \frac{z-z_j}{1-\overline{z_j}z} }. $$ Are its singularities removable? What is $|g|$ as your approach $\partial \mathbb{D}$?
</details>
</li>
<li>
b) If $N = \infty$ and $f \ne 0$ then show that \[ \sum_{j=1}^\infty (1-|z_j|) < \infty
<details>
	<summary>Hint</summary>
	
</details>
</li></ol>

Problem 1 (Prelim January 2019)
------
Given $z\in \mathbb{C}$ and a closed curve in $\mathbb{C}\setminus \\{z\\}$ denote $n(\gamma,z)$ the index or winding number of $\gamma$ about $z$. 
If $\gamma$ can be written as \[ \gamma(t) = \sum_{k = -N}^{N} c_ke^{ikt} \]
with $c_{-N}$ and $c_N$ not both zero show that $-N \leq n(\gamma, z) \leq N$. 
<details>
	<summary>Hint</summary>
	Can you relate this integral to an application of the argument principle on a suitable function?
</details>

Problem 1 (Prelim January 2017)
------
Prove that the range of the entire function $z\mapsto z^2 + \cos(z)$ is all of $\mathbb{C}$
<details>
	<summary>Hint</summary>
	Picard's theorem tells us that this functions range can exclude at most one value. 
</details> 

Problem 1 (Prelim January 2011)
------
Let $f$ be analytic in an anulus $ U = \\{z: r < |z| < R\\}$ where $0 < r < R$. 
Assume $f$ has no zeros in $U$. Show there exists an integer $n$ and a holomorphic function $g:U\to \mathbb{C}$ such that $f(z) = z^n e^{g(z)}
<details>
	<summary>Hint</summary>
	What conditions must $f$ satisfy for this to be true with $n = 0$? If $\gamma$ is a simple closed curve in $U$ then what is the index $n(f\circ \gamma,0)$? Does it depend on $\gamma$?
</details> 

Problem 1 (Prelim January 2016)
------
Show that the equation $\sin(f(z)) = z$ has a solution $f$ that is analytic on the region $U = \\{z\in \mathbb{C}:|z| < 1\text{ or }\text{Im}(z) \ne 0\\}$. 
<details>
	<summary>Hint</summary>
	Write $\sin(w)$ in terms of $e^{iw}$ and solve for it. What properties must be met to have a branch of $\log$ in $U$?
</details>

Problem 1 (Prelim August 2016)
------
Evaluate the integrals  \[  I = \int_C \sqrt{1-z^2}\,dz \quad J = \int_{0}^\infty \frac{x\sin \pi x}{1-x^2}\,dx \] for some branch of the square root function (indicate which) and $C$ is the positively oriented circle $|z| = 2$. 
<details>
	<summary>Hint</summary>

</details>



Problem 1 (Prelim January 2014)
------
Suppose $f$ is an entire function with the property that $f(z)$ is real if and only if $z$ is real. Show that $f'(z) \ne 0$ for all real $z$. 
<details>
	<summary>Hint</summary>
	If $f'(w) = 0$ consider applying the argument principle to $f(w) - w$. 
</details`>
