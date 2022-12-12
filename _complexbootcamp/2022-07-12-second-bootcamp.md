---
title: 'Complex Bootcamp Exercises: Conformal Maps'
date: 2022-07-12
permalink: /complex-prelim-bootcamp/2022/07/bootcamp-2022-ex-2/
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
<details>
	<summary>Solution</summary>
	These two curves intersect at $z = 1$ so using the map $z \mapsto 1/(z-1)$ both circles will map to the lines $i\mathbb{R} -1/2$ and $i\mathbb{R} - 1$, respectively. 
	We can apply a linear transformation to turn the strip between these two lines into $\{x + iy: x \in \mathbb{R}, 0 < y < \pi\}$. 
	From here observe that for values in this set $x+iy \mapsto e^{x+iy} = e^xe^{iy}$ delivers us the upper half plane. 
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
	Note that any map $\mathbb{D} \to \mathbb{D}$ that has no zeros must be constant. 
	If $T$ is our self map and $T(a) = 0$ make another map $S$ of the form above with $z_0 = a$. Then $T\circ S^{-1}$ is a self map which fixes zero. 
</details>
<details>
	<summary>Solution</summary>
	Following the hint, if there exists a point $z\in \mathbb{D}\setminus \{0\}$ such that $|T\circ S^{-1}(z)| = |z|$ then by the Schwarz lemma $T\circ S^{-1}(z) = \alpha z$ for some $|\alpha| = 1$.
	Hence $T = \alpha S(z)$. <br>
	If no such point exists then selecting any $z \in \mathbb{D} \setminus \{0\}$ we must have $|T\circ S^{-1}(z)| < |z|$, but then note that $(T\circ S^{-1})^{-1}$ is another self map of the disk.
	Letting $w = T\circ S^{-1}(z)$ we see $$|z| = | (T\circ S^{-1})^{-1}(w)| \leq |w| < |z|$$ by the first inequality, hence no such $z$ exists. 
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
<details>
	<summary>Solution</summary>
	Taking $U$ to be the disk define $T= \phi_1^{-1} \circ \phi_2$. 
	This is then a self map with the two fixed points $z_i$. 
	Conjugating with a map $S$ of the form from problem 4 which maps $z_1 \mapsto 0$ we can take define $T' = S\circ T \circ S^{-1}$. 
	This map now has the fixed points $0$ and $S(z_2)$. 
	The Schwarz lemma allows us conclude $T'(z) = \alpha z$ with $|\alpha| = 1$, and since $S(z_2)$ is fixed we must have $\alpha = 1$. 
	Hence $T$ is the identity. <br>
	Finally, if $U$ is not the disk then the Riemann mapping theorem provides a biholomorphic map $R:U\to \mathbb{D}$ which sends $z_1 \mapsto 0$. 
	From here, we see $R\circ T\circ R^{-1}$ fixes $0$ and $R(z_2)$ and we can repeat this same argument. 
</details>

Problem 6 (Prelim August 2013)
------
Find all conformal self-maps of $U = \\{z: |z| > 0\\}$. 
<details>
	<summary>Hint</summary>
	Given a self map of $U$ we see it must either be bounded near $0$ or unbounded near zero. 
</details>
<details>
	<summary>Solution</summary>
	Let $T$ be such a map. If it is bounded near 0 we can extend it to a map $T:\mathbb{C} \mapsto \mathbb{C}$. 
	To proceed, we must determine what $T(0)$ is.
	Suppose that $T(0) \ne 0$. 
	Then the original map has a preimage $a\in U$ and it follows by continuity that neighborhoods of $0$ and $a$ both map into neighborhoods of $T(a) = T(0)$, contradicting injectivity of our original map. 
	Hence $T(0) = 0$. 
	This makes $T$ a self map of $\mathbb{C}$ which must be a Möbius transformation fixing $0,\infty$, hence $T(z) = \alpha z$ for some $\alpha \ne 0$.
	<br>
	For the second case suppose that $T$ is a self map that is unbounded near zero. 
	Note that since $T$ never attains the value zero the map $1/T:U\to U$ is then a self map that is bounded near $z = 0$. 
	Hence in this case $T = \alpha z^{-1}$ for an $\alpha \ne 0$. 
</details>

Problem 7 (Prelim August 2021)
------
Find all conformal self maps of the half plane $H = \\{z: \text{Re}(z) > 0\\}$ such that $f(1/2) = 2$ and $f(2) = 1/2$. 
<details>
	<summary>Hint</summary>
	If you cannot think of a satisfactory self map try the transformation from $H$ to the disk $\mathbb{D}$. 
</details>
<details>
	<summary>Solution</summary>
	After some guess work you may find that $f(z) = 1/z$ is one such map (or if you followed the hint, on the unit disk $z\mapsto -z$ would be our candidate.)
	It follows from problem 5 that $f$ is the unique map with this property. 
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
<details>
	<summary>Solution</summary>
	Let $R:U\to \mathbb{D}$ be the Riemann map fixing $0$. 
	Then $g = R\circ f \circ R^{-1}$ is a map on the disk satisfying $g(0) = 0, |g'(0)| < 1$. 
	Applying the Schwarz lemma we have $|g(z)| < |z|$ for all $z \ne 0$. 
	Given any compact set $K\subset \mathbb{D}$ there exists a maximum value $c =  |g(z)/z|$ by continuity. 
	Therefore, $|g(z)| \leq c|z|$ with $c < 1$ providing our strong contraction. 
	Hence the corresponding sequence of functions $g_n$ have the property that $g_n \to 0$ uniformly on compact subsets of $\mathbb{D}$. 
	Conjugating with $R^{-1}$ we then see that $f_n = R^{-1} g_n R \to 0$ uniformly on compact subsets of $U$. 
</details>



Problem 9 (Prelim January 2002)
------
Let $f:D\to \mathbb{C}$ be a holomorphic function satisfying $\text{Re}(f(z)) > 0$ for all $z\in D$ where $D\subset \mathbb{C}$. Show that there exists bounded holomorphic functions $g,h:D\to \mathbb{C}$ such that $$ f(z) = \frac{g(z)}{h(z)} $$
<details>
	<summary>Hint</summary>
	Consider the transformation between a half plane and the disk. 
</details>
<details>
	<summary>Solution</summary>
	The Möbius transformation $$ S(z) = \frac{z - 1}{z + 1}$$ maps between the right half plane onto $\mathbb{D}$. 
	We see that $S\circ f$ is now a holomorphic map from $D$ into $\mathbb{D}$. 
	The inverse of this transformation is 
	$$ S^{-1}(z) = \frac{z+1}{1-z}$$
	This encourages us to define $$ g(z) = S\circ f(z) + 1\quad h(z) = 1 - S\circ f(z) $$
	which are bounded as $S\circ f$ is bounded. It immediately follows that $g/h = S^{-1}\circ S \circ f = f$ as desired. 
</details>


Problem 10 (Prelim January 2017)
------
Find all conformal self maps of $\mathbb{C} \setminus \\{0,1\\}$. 
<details>
	<summary>Hint</summary>
	Since the map must be bijective we determine the orders of the poles at $0, 1, \infty$ and whether or not they are removable. 
	Additionally, use the fact that all self maps of $\mathbb{C}$ are Möbius transformations. 
</details>
<details>
	<summary>Solution</summary>
	At these three points we must have at least one pole/singularity (for, if not, the map will be bounded contradicting surjectivity.) 
	It follows any of these must be simple poles, for poles of order $n > 1$ yield $n$ solutions to $f(z) = w$ for $w$ in a neighborhood of $\infty$ and $z$ in a neighborhood of the pole. 
	Additionally, there is at most one pole (else points with substantially high norm will have two preimages around both poles.)
	It then follows that the remaining two points must be removable singularities, since the function will be bounded in neighborhood of them. 
	By the argument in problem 6 if we extend the map at these singularities they must map to one of $0$ or $1$.
	This extended map is then a conformal self map of all of $\mathbb{C}$ and hence is a Möbius transformation permuting $0,1,\infty$. 
	Since there are six permutations of these points we find the six maps
	$$ \begin{align*}
	0\mapsto 0, 1\mapsto 1, \infty \mapsto \infty & \quad z \\
	0\mapsto 1, 1\mapsto 0, \infty \mapsto \infty & \quad 1 - z \\
	0\mapsto \infty, 1\mapsto 1, \infty \mapsto 0 & \quad \frac{1}{z} \\
	0 \mapsto 0, 1 \mapsto \infty, \infty \mapsto 1 & \quad \frac{z}{z-1} \\
	0\mapsto 1 \mapsto \infty \mapsto 0 & \quad \frac{1}{1-z} \\
	0 \mapsto \infty \mapsto 1 \mapsto 0 & \quad \frac{z - 1}{z}
	\end{align*}$$
</details>
