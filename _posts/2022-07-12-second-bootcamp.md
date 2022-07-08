---
title: 'Complex Bootcamp Exercises: Conformal Maps'
date: 2022-07-12
permalink: /posts/2022/07/bootcamp-2022-ex-2/
tags:
  - bootcamp
  - complex analysis
---

This set of problems focuses on conformal mappings. 

Resources
------
Ahlfors chapter 3 (primarily 3.3, 3.4) and section 6.1.1 (the Riemann mapping theorem.) We will also assume the Schwarz lemma for the prelim problems (which is often necessary to show certain maps are Möbius maps) section 4.3.4 theorem 13.

Problems
======

Problem 1 (Ahlfors 3.4.2.2)
------
Map the region between $|z| = 1$ and $|z-1/2| = 1/2$ on a half plane. 
<details>
	<summary>Hint</summary>
	
</details>

Problem 1 (Ahlfors 3.4.2.1)
------
Map the common region of $|z| = 1$ and $|z-1| = 1$ on the inside of a circle. 
<details>
	<summary>Hint</summary>
	
</details>

Problem 1 (Palka 6.12)
------
Find a conformal map from $D = \\{z: |\text{Re}(z)| + |\text{Im}(z)| < \sqrt{2}/2\\}$ to $D' = \\{z: 1 < |z| < e^\pi, \text{Im}(z) >0 \\}$.
<details>
	<summary>Hint</summary>
	
</details>

Problem 1
------
Show that all conformal self maps of $\mathbb{D} = \\{z: |z| < 1\\}$ are of the form $$ z\mapsto \alpha \frac{z - z_0}{1-\overline{z_0} z} $$ for a $z_0 \in \mathbb{D}$ and $|\alpha| = 1$. 
<details>
	<summary>Hint</summary>
	If $T$ is our self map and $T(a) = 0$ make another map $S$ of the form above with $z_0 = a$. Then $T\circ S^{-1}$ is a self map which fixes zero. 
</details>

Problem 1
------
Let $U\subset \mathbb{C}$ be a simply connected open subset. 
Suppose $\phi_1,\phi_2:U\to U$ are two conformal self maps and there exists $z_1,z_2$ such that $\phi_1(z_i) = \phi_2(z_i)$. 
Show that $\phi_1 = \phi_2$. 
<details>
	<summary>Hint</summary>
	First attempt this problem on the unit disk then extend this result to other regions via the Riemann mapping theorem. 
</details>

Problem 1 (Prelim August 2013)
------
Find all conformal self-maps of $U = \\{z: |z| > 0\\}$. 
<details>
	<summary>Hint</summary>
	Transform this into a problem of self maps on the punctured disk. Since any such map is bounded the singularity at the isolated point is removable.
	Extend the function on this singularity and show it results in a self map of the disk. 
</details>

Problem 1 (Prelim August 2021)
------
Find all conformal self maps of the half plane $H = \\{z: \text{Re}(z) > 0\\}$ such that $f(1/2) = 2$ and $f(2) = 1/2$. 
<details>
	<summary>Hint</summary>
	Use the transformation between $H$ and the unit disk $\mathbb{D}$ to rephrase this problem on the disk. 
</details>

Problem 1 (Prelim August 2015)
------
Let $U\subset \mathbb{C}$ be a bounded simply connected region with $0\in U$. Suppose $f:U\to U$ is a holomorphic function satisfying $f(0) = 0$, $|f'(0)| < 1$. 
We can define the sequence of functions $\\{f_n\\}_{n=1}^\infty$ by $$ f_n(z) = \underbrace{f\circ \cdots \circ f}_\text{$n$ times}(z) $$
show that $f_n \to 0$ uniformly on compact subsets of $U$. 
<details>
	<summary>Hint</summary>
	Apply the Riemann mapping theorem so that we can take $U = \mathbb{D}$, the open unit disk centered at 0. <br>

	Since we can take $U$ to be the disk we can apply the Schwarz lemma, giving us that $|f(z)| < |z|$ for all $z \in \mathbb{D}\setminus \{0\}$. Use this to construct a strong contraction over compact subsets of $U$. 

</details>




Problem 1 (Prelim January 2002)
------
Let $f:D\to \mathbb{C}$ be a holomorphic function satisfying $\text{Re}(f(z)) > 0$ for all $z\in D$ where $D\subset \mathbb{C}$. Show that there exists bounded holomorphic functions $g,h:D\to \mathbb{C}$ such that $$ f(z) = \frac{g(z)}{h(z)} $$
<details>
	<summary>Hint</summary>
	Consider the transformation between a half plane and the disk. 
</details>


