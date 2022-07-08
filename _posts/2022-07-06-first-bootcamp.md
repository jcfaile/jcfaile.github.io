---
title: 'Complex Bootcamp Exercises: Basics of Holomorphic Functions'
date: 2022-07-06
permalink: /posts/2022/07/bootcamp-2022-ex-1/
tags:
  - bootcamp
  - complex analysis
---

Welcome to the complex analysis bootcamp. In this first set of problems we focus on basic properties of holomorphic functions and work up to branches of functions. 

Resources
------
Ahlfors chapter 2 and section 3.2.2

Problems
======

Problem 1
------
Suppose $f$ is an entire function satisfying that $f(z) = f(z + t\xi)$ for some nonzero constant $\xi \in \mathbb{C}$ and all $t\in \mathbb{R}$. Show that $f$ is constant. 
<details>
	<summary>Hint</summary>
	Suppose that $\xi = 1$ and compute $\partial f/\partial x$. Use the Cauchy-Riemann equations to reach the desired conclusion. 
</details>
<details>
	<summary>Solution</summary>
	Supposing that $\xi = 1$ and writing $f(z) = u(z) + iv(z)$ (where $u,v:\mathbb{C} \to \mathbb{R}$) we find $$ \frac{\partial u}{\partial x} = \frac{\partial v}{\partial x} = 0$$ and by the Cauchy-Riemann equations it follows that the $y$ partials are also zero. 
	Hence $u,v$ are constant functions giving us the desired result. 

	In the case that $\xi \ne 1$ define $g(z) = f(\xi z)$, then $g(z+t) = f(\xi z + t\xi) = f(\xi z) = g(z)$ so $g$ is an entire function satisfying our prior assumptions, and hence is constant.
</details>

Problem 2 (Ahlfors 2.1.4.4)
------
What is the general form of a rational function $R$ satisfying $|R(z)| = 1 $ for all $ |z| = 1 $? How are the zeros and poles of $R$ related to one another?
<details>
	<summary>Hint</summary>
	We know that \(z = 1/\overline{z}\) when \(|z| = 1\) so \( \overline{R(z)} = \overline{R(1/\overline{z})}\) on \(|z| = 1\).
	Can you establish what relationship \(R(z)\) and \(\overline{R(1/\overline{z})}\) have when $|z| \ne 1$?
</details>
<details>
	<summary>Solution</summary>
	As outlined in the hint, $$1 = |R(z)|^2 = R(z) \overline{R(z)} = R(z)\overline{R\left(\frac{1}{\overline{z}}\right)} $$ on the circle $|z| = 1$. 
	Note that due to the double conjugation on $\overline{R(1/\overline{z})}$ this is a rational function of $z$, and hence so is its product with $R(z)$. 
	Note that since an infinite number of points satisfy $|z| = 1$ it must follow that the above equality holds on all of $\mathbb{C}$ (if any two rational functions are equal on an infinite number of points then they are equal, for if not we could produce a finite degree polynomial with an infinite number of roots.)
	Hence we have 
	$$ R(z) = \left[\overline{R\left(\frac{1}{\overline{z}}\right)}\right]^{-1} $$ for all $z$ that are not poles of $R(z)$. 
	From here, we see that $R$ has a root at some $z\in\mathbb{C}$ with order $m$ if and only if $R$ has a pole at $\overline{z}^{-1}$ of order $m$. 
	This completely describes all roots and poles of $R$, so we are encouraged to define a rational function
	$$ S(z) = \prod_{i = 1}^n \left(\frac{z-z_i}{1-\overline{z_i}z}\right)^{m_i} $$
	where the $\{z_i\}_{i=1}^n$ are the distinct roots of $R$ with order $\{m_i\}_{i=1}^n$. 
	Computing $R(z)/S(z)$ we see that since $R(z)$ and $S(z)$ have the same roots/poles with the same orders their quotient must not have any roots or poles. 
	The only rational functions with this property are nonzero constants, so let $R(z)/S(z) = \alpha \in \mathbb{C}\setminus \{0\}$. 
	Finally, since $|R(z)| = 1$ when $|z| = 1$ we deduce $|\alpha| = 1$ hence the general form is 
	$$R(z) = \alpha S(z) = \alpha \prod_{i = 1}^n \left(\frac{z-z_i}{1-\overline{z_i}z}\right)^{m_i}$$
</details>


Problem 3 (Ahlfors 2.1.4.5)
------
What is the general form of a rational function $R$ satisfying $R(z) \in \mathbb{R}$ for all $|z| = 1$? How are the zeros and poles of $R$ related to one another?
<details>
	<summary>Hint</summary>
	As in the last problem, we can deduce a relationship between \(R\) and \(\overline{R(1/\overline{z})}\) now using the additional fact that \(\overline{R(z)} = R(z)\). 
</details>
<details>
	<summary>Solution</summary>
	First, we see that if $R = 0$ then it is of this desired form. Suppose for the rest of this that $R \ne 0$.
	Similar to the last problem, we find the relationship
	$$R(z) = \overline{R(z)} = \overline{R\left(\frac{1}{\overline{z}}\right)} $$
	which, by the same reasoning, is equal for all $z$ in the domain of $R$. 
	We then find that $z$ is a root (resp. pole) of order m of $R$ if and only if $\overline{z}^{-1}$ is also root (resp. pole) of order $m$. 
	Following similar steps to problem 2 we find
	$$ R(z) = \alpha z^k\prod_{i=1}^n (z-z_i)^{o_i}(z-\overline{z_i}^{-1})^{o_i} \prod_{i=1}^n (z-\xi_i)^{p_i} $$
	for the distinict roots and poles $\{z_i\}_{i=1}^n$ of orders $o_i$ (where this value is negative for poles) with $|z_i| < 1$ and $\{\xi_i\}_{i=1}^n the roots/poles with $|\xi_i| = 1$ of orders $p_i$, and this time we find $\alpha \in \mathbb{R}\setminus \{0\}$. 
</details>

Problem 4 (Ahlfors 2.2.4.2)
------
Write \[ \frac{2z+3}{z+1} \] as a power series in terms of $z-1$. Find the radius of convergence for this series. 
<details>
	<summary>Hint</summary>
	Algebraically manipulate the expression so you can use the geometric series formula $$ \frac{1}{1-r} = \sum_{n=0}^\infty r^n $$ where \(r\) is an expression containing $z-1$. 
</details>
<details>
	<summary>Solution</summary>
	$$ \begin{align*} 
		\frac{2z+3}{z+1} &= \frac{2z+2}{z+1} + \frac{-1}{z+1} \\
		&= 2 - \frac{1}{2-(1-z)} \\
		&= 1 - \frac{1}{2} \frac{1}{1 - \frac{1-z}{2}} \\
		&= 1 - \frac{1}{2} \sum_{n=0}^\infty \left( - \frac{1}{2}\right)^n (z-1)^n
	\end{align*} $$
	for $n > 0 $ we see $|a_n| = 1/2^{n+1}$, so 
	$$ 1/R = \limsup \sqrt[n]{1/2^{n+1}} = 1/2 $$ giving a radius of convergence of 2. 
</details>

Problem 5 (Ahlfors 3.2.2.2)
------
Give a precise definition of a branch of the function $\log \log(z)$. 

<details>
	<summary>Solution</summary>
	Define $U = \mathbb{C} \setminus \Ahlfors 2.1.4.5{z\in \mathbb{R}: z \leq 1\}$ then restrict the principle branch of $\log$ to $U$. 
	We see $\log(U) = \{x+iy: x > 0\text{ or } 0 < |y| < \pi\}$ which lies in the domain of the principle branch of $\log$, hence our definition of $\log \log:U\to \mathbb{C}$ is a well defined single valued branch.
</details>


Problem 6 (Ahlfors 3.2.2.3)
------
Suppose $f$ is a holomorphic function satisfying $|f(z)^2 - 1| < 1$ for all $z \in \Omega$ a connected open subset of $\mathbb{C}$. Prove that either $\text{Re}(f(z)) > 0$ or $\text{Re}(f(z)) < 0$ for all $z\in \Omega$. 
<details>
	<summary>Hint</summary>
	Consider the branches of $\sqrt{z}$ that you can define on the ball of radius 1 centered at 1. 
	What can you deduce about the set of points $w$ satisfying $|w^2 - 1| < 1$?
</details>
<details>
	<summary>Solution</summary>
	Following the hint, define two branches of $\sqrt{z}$ as maps $s_1,s_2:\mathbb{C} \setminus \{a\in \mathbb{R}: a < 0\} \to \mathbb{C}$ by choosing one to be the principle branch of square root ($s_1$) and the other its negative ($s_2$). 
	$s_1$ has codomain the half plane with $\text{Re}(z) > 0$ while $s_2$ has codomain the opposite half plane $\text{Re}(z)<0$. 
	Now, if $|w^2 - 1| < 1$ we see that $w^2 \in B_1(1)$. 
	This ball is contained in the domains of both $s_1,s_2$ and applying them to this set we find $s_1(B_1(1))$ is in the half plane $\text{Re}(z) > 0$ while $s_2(B_1(1))$ is in the half plane $\text{Re}(z) < 0$ and since the ball is connected we see its square roots are as well. 
	Finally, since $\Omega$ is connected we must have that $f(\Omega)$ is connected, so $f(\Omega)\subset s_i(B_1(1))$ for one of $i = 1, 2$. 
</details>

Problem 7 (Prelim January 2014)
------
Let $U\subset\mathbb{C}$ be open and define $V = \\{z:z^4 \in U\\}$. 
Suppose $f: V \to \mathbb{C}$ is a holomorphic function satisfying $f(iz) = f(z)$ for all $z \in V$. 
Prove that there exists a holomorphic function $g:U \to \mathbb{C}$ such that $f(z) = g(z^4)$ for all $z\in V$. 
<details>
	<summary>Hint</summary>
	Intuitively this is solved if we can let $g(z) = f(\sqrt[4]{z})$, but this is ill-defined unless we work with branches of $\sqrt[4]{z}$. 
	Define two separate branch cuts of $\sqrt[4]{z}$ to find different candidates of $g(z)$ defined on different domains. Try to "combine" these into one function. <br>


	You may find that this process only defines $g$ on $V\setminus\{0\}$ due to both branch cuts excluding zero. 
	Recall that such a function can be extended analytically to 0 if $\lim_{z\to 0} zg(z) = 0$ (removable singularities; Ahlfors 4.3.1.) 
</details>
<details>
	<summary>Solution</summary>
	Let $ V_1 = \mathbb{C} \setminus \{a\in \mathbb{R}: a < 0\} $ and $V_2 = \mathbb{C} \setminus \{ia\in i\mathbb{R}: a < 0\}$. 
	Define $s_1:V_1\to \mathbb{C}$ as the principle branch of $\sqrt[4]{z}$ and $s_2:V_2\to \mathbb{C}$ by $re^{i\theta} \mapsto \sqrt[4]{r}e^{i\theta / 4}$ for $r > 0$ and $-\pi/2 < \theta < 3\pi/2$. 
	We then find that $g_i = f\circ s_i:V\cap V_i \to \mathbb{C}$ satisfies $f(z) = g_i(z^4)$ when $z^4$ is in the domain of $g_i$ (note that this requires our hypothesis that $f(z) = f(iz)$, for if $z$ is in the domain of any two branches of $\sqrt[4]{z}$ then the branches will differ by a factor of $i^k$.) 
	This also means that $g_1 = g_2$ on $V\cap V_1 \cap V_2$. 
	We can now extend both of these to $g:V\setminus \{0\} \to \mathbb{C}$ by defining $g(z) = g_1(z)$ for all $z \in V_1$ and $g(z) = g_2(z)$ when $z \in \mathbb{R}^{-}$. 
	At every point in the domain $g$ is holomorphic, because we can construct a neighborhood of $z$ with $g= g_i$. 
	Finally, we note that if $0 \in V$ then $0 \in U$ and we can select a neighborhood of $0$ such that $f$ is bounded. 
	We then see that as $z\to 0$ we have $s_i(z) \to 0$ so $f(z)$ must remain bounded. Hence $\lim_{z\to 0} zf(z) = 0$ and the singularity at zero is removable, so we can extend $g$ analytically to a map $V\to \mathbb{C}$.
		Finally, since $s_i(z) \to 0$ as $z\to 0$ we find $g(0) = g(0^4) = f(0)$ showing $g(z^4) = f(z)$ for all $z \in V$ as desired. 
</details>
