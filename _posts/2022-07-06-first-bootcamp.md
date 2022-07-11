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
Suppose $R$ is a rational function satisfying $R(z) \in \mathbb{R}$ for all $|z| = 1$. How are the zeros and poles of $R$ related to one another?
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
	We then find that $z$ is a root (resp. pole) of order $m$ of $R$ if and only if $\overline{z}^{-1}$ is also root (resp. pole) of order $m$. 
	This allows us to classify all poles/roots if we know all poles/roots $z$ with $|z| \leq 1$, where $0 < |z| < 1$ come in pairs $(z,\overline z^{-1})$ and $|z| = 1$ are single roots. (Note - unlike the last problem its much more difficult to find the general form of these maps. This is because our rational factors $(1-z)(1-\overline{z}^{-1})$ aren't themselves maps sending the circle to the reals.)
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
	$$ 1/R = \limsup_{n\to\infty} \sqrt[n]{1/2^{n+1}} = 1/2 $$ giving a radius of convergence of 2. 
</details>

Problem 5 (Ahlfors 3.2.2.2)
------
Give a precise definition of a branch of the function $\log \log(z)$. 

<details>
	<summary>Solution</summary>
	Define $U = \mathbb{C} \setminus \{z\in \mathbb{R}: z \leq 1\}$ then restrict the principle branch of $\log$ to $U$. 
	We see $\log(U) = \{x+iy: |y| < \pi\} \setminus \mathbb{R}^-$ which lies in the domain of the principle branch of $\log$, hence our definition of $\log \log:U\to \mathbb{C}$ is a well defined single valued branch.
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


	You may find that this process only defines $g$ on $U\setminus\{0\}$ due to both branch cuts excluding zero. 
	Recall that such a function can be extended analytically to 0 if $\lim_{z\to 0} zg(z) = 0$ (removable singularities; Ahlfors 4.3.1.) 
</details>
<details>
	<summary>Solution</summary>
	As mentioned in the hint, we wish to rigorously write $g(z) := f(\sqrt[4]{z})$ for $z \in U$. 
	Let $$ U_1 = \mathbb{C} \setminus \{ z: z \in \mathbb{R}^{-} \} \quad \text{and} \quad U_2 = \mathbb{C} \setminus \{z: z \in i\mathbb{R}^{-} \} $$
	Define the two functions $s_1:U_1\to \mathbb{C}$ the principle branch of $\sqrt[4]{z}$ and $s_2:U_2\to \mathbb{C}$ by $re^{i\theta} \mapsto \sqrt[4]{r}e^{i\theta / 4}$ for $r > 0$ and $-\pi/2 < \theta < 3\pi/2$. 
	Note that since $(s_i(z))^4 = z$ we have that $z \in U \implies s_i(z) \in V$, hence on $U_i$ the function $g_i = f\circ s_i$, $i = 1,2$ is well defined. 
	Now if $z \in U_1\cap U_2$ it is possible that $s_1(z) \ne s_2(z)$, but they may differ only by a power of a forth root of unity. 
	Therefore, $$ g_1(z) = f(s_1(z)) = f(i^ks_2(z)) = f(s_2(z)) = g_2(z) $$ showing the $g_i$ agree on $U_1\cap U_2$. 
	As a result of this we can define $g:U\setminus \{0\} \to \mathbb{C}$ by $g(z) = g_1(z)$ for all $z\in U_1$ and $g(z) = g_2(z)$ for $z \notin U_2$ and $z \ne 0$. 
	This resulting function is holomorphic, because for every $z$ we can select a neighborhood where $g = g_i$. 
	Finally, if $0 \in U$ then $0\in V$ and since $f$ is holomorphic we can select a neighborhood of $0$ where $f$ is bounded. 
	This allows us to evaluate the limit $$ \lim_{z\to 0} zg(z) = \lim_{z\to 0} zf(s_i) = \lim_{z\to 0} zM = 0$$ where $M$ is the bound of $f$ in the neighborhood of zero. 
	This shows that the singularity of $g$ at zero is removable and we can extend $g$ holomorphically to all of $U$. 
	Finally, taking the limit as $z\to 0$ of the identity $g(z^4) = f(z)$ we see the right hand side converges to $f(0)$ while the left converges to $g(0)$, showing that this identity holds over all of $U$ as desired. 

</details>
