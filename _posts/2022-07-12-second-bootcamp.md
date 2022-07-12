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
Ahlfors chapter 3 (primarily 3.3, 3.4) and section 6.1.1 (the Riemann mapping theorem.) We will also assume the Schwarz lemma for some problems (section 4.3.4 theorem 13.)

Problems
======

Problem 1 (Ahlfors 3.4.2.2)
------
Map the region between $|z| = 1$ and $|z-1/2| = 1/2$ on a half plane. 
<details>
	<summary>Hint</summary>
	Invert at the common point to map both circles to half planes. 
</details>

Problem 2 (Ahlfors 3.4.2.1)
------
Map the common region of $|z| = 1$ and $|z-1| = 1$ on the inside of a circle. 
<details>
	<summary>Hint</summary>
	Invert at a common point to map both circles to half planes. 
</details>

Problem 3 (Palka 6.12)
------
Find a conformal map from $D = \\{z: |\text{Re}(z)| + |\text{Im}(z)| < \sqrt{2}/2\\}$ to $D' = \\{z: 1 < |z| < e^\pi, \text{Im}(z) >0 \\}$.


Problem 4
------
Show that all conformal self maps of $\mathbb{D} = \\{z: |z| < 1\\}$ are of the form $$ z\mapsto \alpha \frac{z - z_0}{1-\overline{z_0} z} $$ for a $z_0 \in \mathbb{D}$ and $|\alpha| = 1$. 
<details>
	<summary>Hint</summary>
	Note that any map $\mathbb{D} \to \mathbb{D}$ that have no zeros must be constant. 
	If $T$ is our self map and $T(a) = 0$ make another map $S$ of the form above with $z_0 = a$. Then $T\circ S^{-1}$ is a self map which fixes zero. 
</details>

Problem 5
------
Let $U\subsetneq \mathbb{C}$ be a simply connected open subset of $\mathbb{C}$. 
Suppose $\phi_1,\phi_2:U\to U$ are two conformal self maps and there exists $z_1,z_2$ such that $\phi_1(z_i) = \phi_2(z_i)$. 
Show that $\phi_1 = \phi_2$. 
<details>
	<summary>Hint</summary>
	First attempt this problem on the unit disk then extend this result to other regions via the Riemann mapping theorem. 
</details>

Problem 6 (Prelim August 2013)
------
Find all conformal self-maps of $U = \\{z: |z| > 0\\}$. 
<details>
	<summary>Hint</summary>
	Transform this into a problem of self maps on the punctured disk. Since any such map is bounded the singularity at the isolated point is removable.
	
</details>

Problem 7 (Prelim August 2021)
------
Find all conformal self maps of the half plane $H = \\{z: \text{Re}(z) > 0\\}$ such that $f(1/2) = 2$ and $f(2) = 1/2$. 
<details>
	<summary>Hint</summary>
	If you cannot think of a satisfactory self map try the transformation from $H$ to the disk $\mathbb{D}$. 
</details>

Problem 8 (Prelim August 2015)
------
Let $U\subsetneq \mathbb{C}$ be a bounded simply connected region with $0\in U$. Suppose $f:U\to U$ is a holomorphic function satisfying $f(0) = 0$, $|f'(0)| < 1$. 
We can define the sequence of functions $\\{f_n\\}_{n=1}^\infty$ by $$ f_n(z) = \underbrace{f\circ \cdots \circ f}_\text{$n$ times}(z) $$
show that $f_n \to 0$ uniformly on compact subsets of $U$. 
<details>
	<summary>Hint 1</summary>
	Apply the Riemann mapping theorem so that we can take $U = \mathbb{D}$.
</details><details>
	<summary>Hint 2</summary>
	Since we can take $U$ to be the disk we can apply the Schwarz lemma, giving us that $|f(z)| < |z|$ for all $z \in \mathbb{D}\setminus \{0\}$. Use this to construct a strong contraction over compact subsets of $U$. 

</details>




Problem 9 (Prelim January 2002)
------
Let $f:D\to \mathbb{C}$ be a holomorphic function satisfying $\text{Re}(f(z)) > 0$ for all $z\in D$ where $D\subset \mathbb{C}$. Show that there exists bounded holomorphic functions $g,h:D\to \mathbb{C}$ such that $$ f(z) = \frac{g(z)}{h(z)} $$
<details>
	<summary>Hint</summary>
	Consider the transformation between a half plane and the disk. 
</details>

Problem 10 (Prelim January 2017)
------
Find all conformal self maps of $\mathbb{C} \setminus \\{0,1\\}$. 
<details>
	<summary>Hint</summary>
	Since the map must be bijective we determine the orders of the poles at $0, 1, \infty$ and whether or not they are removable. 
	Additionally, use the fact that all self maps of $\mathbb{C}$ are Möbius transformations. 
</details>
