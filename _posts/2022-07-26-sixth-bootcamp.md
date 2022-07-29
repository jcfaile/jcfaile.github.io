---
title: 'Complex Bootcamp Exercises: Normal Families'
date: 2022-07-26
permalink: /posts/2022/07/bootcamp-2022-ex-6/
tags:
  - bootcamp
  - complex analysis
---

This set of problems focuses on normal families (precompact sets of functions,) Picard's theorem, Jensen's formula, and other topics.

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
	Recall an entire function $f$ is a polynomial if and only if $|f(z)| \to \infty$ as $z \to \infty$. <br>
	This problem is using the notion of ``normal families'' for meromorphic functions, so having a sequence of holomorphic functions converging to the constant map $z\mapsto \infty$ is possible.  
</details>
<details>
	<summary>Solution</summary>
	Suppose $f$ is a polynomial and let $\{f_n\}_{n=1}^\infty \subset \mathcal{F}$. 
	We note that we can write every $f_n(z) = f(k_nz)$ for some $k\in \mathbb{C}$. 
	If the set $\{k_n\}_{n=1}^\infty$ is unbounded we may select a subsequence converging to infinity, in which case we have for all $r_1<|z| < r_2$ $k_nz \to \infty$ as $n\to \infty$, and since $f$ is a polynomial we have $f_n \to \infty$ uniformly on compact sets. 
	If the sequence $\{k_n\}_{n=1}^\infty$ is bounded then it itself is precompact, so we can take a subsequence $n_j$ converging to a $k \in \mathbb{C}$. 
	It then follows $f_{n_j} \to g$ where $g(z) = f(kz)$ (this I will not fully prove, but by the triangle inequality it suffices consider just the polynomials $z^k$, $k\in \mathbb{N}$.) 
	<br>


	Now suppose that $\mathcal{F}$ defines a normal family. 
	We can then define the sequence of functions $f_n(z) = f(nz)$ which lie in this family. 
	Since $f$ is entire we see either
	$$ \lim_{n\to\infty} \max_{r_1 < |z| < r_2} |f_n(z)| \to \infty$$
	or else $|f|$ is bounded and hence $f$ is a constant polynomial. 
	In the case that this limit converges to infinity, we must have that $f_n \to \infty$ (because normality in this sense allows holomorphic functions to converge to either other holomorphic functions or the constant map $z\mapsto \infty.$)
	This establishes that 
	$$ \lim_{z\to\infty} |f(z)| = \infty$$
	hence $f$ is a polynomial. 
</details>

Problem 2 (Prelim August 2015)
------
Let $f$ be an entire function satisfying $f(1-z) = 1-f(z)$. Show that $f(\mathbb{C}) = \mathbb{C}.$
<details>
	<summary>Hint</summary>
	Suppose not and apply Picard to find that $f(\mathbb{C}) = \mathbb{C} \setminus \{w\}$. 
</details>
<details>
	<summary>Solution</summary>
	Suppose not, then by Picards theorem there exists $w$ such that $f(\mathbb{C}) = \mathbb{C} \setminus \{w\}$. 
	From our relation, if there exists $z$ such that $f(z) = 1-w$ then $$1-f(z) = 1-(1-w) = w = f(1-z). $$
	By Picards, we are guaranteed such $z$ as long as $1-w \ne w \implies w \ne 1/2$. 
	If $w = 1/2$ note that at $z = 1/2$ we have 
	$$2f(1/2) = f(1-1/2) + f(1/2) = 1$$
	hence $f$ attains $1/2$ and $f(\mathbb{C}) = \mathbb{C}$. 
</details>

Problem 3 (Prelim August 2020)
------
Suppose that $f$ is analytic on $\mathbb{D}$ and satisfies $|f(z)| \leq M$ for all $z\in \mathbb{D}$. Assume further that $f$ vanishes at the points $\\{z_j\\}_{j=1}^N$ where $1 \leq N \leq \infty.$)
If $N = \infty$ and $f \ne 0$ then show that $$ \sum_{j=1}^\infty (1-|z_j|) < \infty. $$
<details>
	<summary>Hint</summary>
	Jensen's formula. 
</details>
<details>
	<summary>Solution</summary>
	Jensen's formula guarantees the convergence of the sum 
	$$ \sum_{j=1}^\infty \log(|z_j|) $$
	and due to the inequality $\log r = \log(1 + (r-1)) \leq r-1$ we find 
	$$ 0 \leq \sum_{j=1} 1- |z_j| \leq -\sum_{j=1}^\infty \log(|z_j|).  $$
</details>

Problem 4 (Prelim January 2022)
------
Let $U,V$ be disjoint non-empty open subset of $\mathbb{C}$. Let $\\{f_n\\}_{n=1}^\infty$ be a sequence of holomorphic functions $f_n : U \to V.$
Show that some subsequence converges locally uniformly to a holomorphic function $f$, and that $f$ is one-to-one if each $f_n$ is one-to-one. <br><i>(Remark added after the exam. An extra condition is missing: $\\{f_n(u)\\}$ is bounded for some $u\in U.)$</i>
<details>
	<summary>Hint</summary>
	Since $U$ and $V$ are disjoint we can transform the sequence into a bounded sequence. 
</details>
<details>
	<summary>Solution</summary>
	Since $U$ is open selecting any $w \in U$ there exists $r>0$ such that $B_r(w) \subset U$. 
	We then define the sequence of functions $g_n:U\to B_{1/r}(0)$ by $g_n(z):= (f(z) - w)^{-1}$. 
	We immediately see that $|g_n(z)| = |f(z) - w|^{-1} < r^{-1}$ hence they form a normal family and we can choose a subsequence converging uniformly on compact sets to $g: U \to \overline{U}$. 
	Next, suppose for some $z$ we have $g(z_0) = 0.$
	Since the functions $f_n$ are holomorphic the functions $g_n$ are never equal to zero (for this requires a pole of $f_n$) and we can apply the minimum modulus principle. 
	Selecting any ball of radius $q$ we see 
	$$ \min_{|z - z_0| < q} |g_n(z)| = \min_{|z-z_0| = q} |g_n(z)| $$
	which when applied to our subsequence converging to $g$ gives us that $g$ has a root in every circle $|z- z_0| = q < r^{-1} - |z_0|$. 
	Any such set of zeros obviously has an accumulation point at $z = z_0$, hence we would have $g \equiv 0.$ 
	However, since $\{f_n(u)\}$ remains bounded we see there exists some $\epsilon > 0$ such that $\epsilon < |g_n(u)|$ ruling out uniform convergence to zero. 
	Now, since we know the image of $g$ is contained within $B_{1/r}(0)\setminus \{0\}$ we can define $$f(z) = w + \frac{1}{g(z)} $$
	and this will be the uniform limit on compact sets of the subsequence of $\{f_n\}_{n=1}^\infty$ corresponding to the subsequence of $\{g_n\}_{n=1}^\infty$ we selected. 
	<br>
	The argument for injectivity is completely contained in the solution to problem 9. 
</details>

Problem 5 (Prelim August 2021)
------
<div>Let $\{ f_n \}_{n=1}^\infty$ be bounded holomorphic functions on $\Omega = \{z\in \mathbb{C}:|z| > 1\}$ that take values in $\Omega.$ 
If the sequences $\{ f_n(k) \}_{n=1}^\infty$ converge for each integer $k > 1$ then show that $\{f_n\}_{n=1}^\infty$ converges uniformly on compact subsets of $\Omega.$</div>
<details>
	<summary>Hint</summary>
	You may need to use the sub-subsequence argument to extend beyond just convergence of subsequences. 
</details>
<details>
	<summary>Solution</summary>
	Letting $I:\mathbb{C}\setminus \{0\} \to \mathbb{C}\setminus \{0\}$ be the inversion map $z\mapsto z^{-1}$ the composition $g_n = I\circ f_n\circ I$ defines a bounded family.
	Note that since $g_n:\mathbb{D} \setminus \{0\} \to \overline{\mathbb{D}}$ the singularity at zero is removable, so here on consider $g_n$ to be the analytic extension. 
	Additionally, we have that $\{g_n(1/k)\}_{n=1}^\infty$ defines a convergent sequence of complex numbers. 
	By Montel's theorem the family $\{g_n\}_{n=1}^\infty$ is normal. 
	Pick any subsequence of $\{g_n\}$, then by normality it has a sub-subsequence converging to some holomorphic function $g:\mathbb{D} \to \overline{\mathbb{D}}$. 
	Suppose we do this process again on a different subsequence, then we recieve a subsequence converging to a $\tilde g$. 
	Now since the sequence $\{g_n(1/k)\}_{n=1}^\infty$ is convergent for every integer $k > 1$ we have
	$$ g\left( \frac{1}{k} \right) = \lim_{n\to \infty} g_{a_n}\left(\frac{1}{k} \right) = \lim_{n\to \infty} g_{b_n}\left(\frac{1}{k} \right) = \tilde g\left( \frac{1}{k} \right).$$
	The set $\{1/k: k \in \mathbb{Z}^{>1}\}$ has an accumulation point $z = 0$ within the domains of $g,\tilde g$ and hence by the identity theorem it follows that $g \equiv \tilde g$. 
	Since every subsequence has a sub-subsequence converging to the same limit we must have this convergence on the entire sequence, $g_n \to g$ uniformly on compact sets.
	Conjugating $g_n$ and $g$ by the inversion map then gives this for $f_n \to f$. 

</details>

Problem 6 (Prelim August 2016)
------
Let $\mathcal{F}$ be the set of all entire functions $f$ with the following properties. The zeros $a_1,a_2,\dots$ of $f$ satisfy $\sum_{n} |a_n|^{-1} \leq 1$. Furthermore, $f(0) = 1$, $|f'(0)| \leq 1$, and $e^{-|z|} |f(z)| \to 0$ as $|z| \to \infty$. Show that every sequence in $\mathcal{F}$ has a subsequence converging uniformly on compact subsets of $\mathbb{C}.$
<details>
	<summary>Hint</summary>
	Knowing that $\sum_{n=1}^N |a_n|^{-1}$ is bounded implies that the product 
	$$ \prod_{n = 1}^N 1 - \frac{z}{a_n} $$
	converges uniformly on compact sets. 
	As a result, a function of genus $h$ with these roots then has the canonical representaiton $$ z^{g(z)}\prod_{n=1}^N 1 - \frac{z}{a_n} $$ where $g(z)$ is a degree $h$ polynomial. 
</details>
<details>
	<summary>Solution</summary>
	From our hypothesis on the sum of roots we see that the genus of any $f\in \mathcal{F}$ is at least zero.
	Since $e^{-|z|}|f(z)| \to 0$ as $|z|\to \infty$ the order is at most one (and in particular the genus is at most $1$ due to Hadamard) hence we can write $f$ as 
	$$ f(z) = Ce^{\alpha z} \prod_{m=1}^N 1-\frac{z}{a_i}$$
	for some $\alpha,C \in \mathbb{C}$.
	We observe $f(0) = C = 1$ and we can estimate $\alpha$ by
	$$\begin{align*} 
		1 \geq |f'(0)| &= \left| \alpha - \sum_{n=1}^N \frac{1}{a_n} \right|\\
		&\geq \left| |\alpha| - \left| \sum_{n=1}^N \frac{1}{a_n} \right| \right|
	\end{align*} $$
	which shows $|\alpha| \leq 1 + |\sum_{n=1}^N a_n^{-1}| \leq 2.$
	Now taking any compact subset of $\mathbb{C}$ we see it is bounded with $|z| \leq M$. 
	From here we can estimate 
	$$ \begin{align*}
		\log |f(z)| &= \text{Re}(\alpha z) + \sum_{n=1}^N \log\left(\left|1-\frac{z}{a_n}\right|\right) \\
		&\leq 2M + \sum_{n=1}^N \frac{M}{a_n} \leq 3M
	\end{align*} $$
	which is bounded by the hypothesis on the roots and the fact that $|\alpha| < 2.$ 
	This shows that $\mathcal{F}$ is locally uniformly bounded and therefore it is normal family by Montel's theorem. 
</details>

Problem 7 (Prelim January 2016)
------
Let $\\{f_n\\}_{n=1}^\infty$ be a sequence of holomorphic functions defined on a domain $\Omega \subset \mathbb{C}$ and assume $f_n\to f$ pointwise on $\Omega$. 
Suppose no $f_n$ ever attains a positive real value. Show that $f$ is holomorphic on $\mathbb{\Omega}.$
<details>
	<summary>Hint</summary>
	Can you conformally map the image set $\mathbb{C} \setminus \mathbb{R}^+$ to a bounded set? 
</details>
<details>
	<summary>Solution</summary>
	Since no $f_n$ attains a value in $\mathbb{R}^+$ let $s:\mathbb{C} \setminus \{z: z\geq 1\}$ be a branch of the square root function with $s(-1) = i$. 
	We then see that $s\circ f_n$ has image in the upper half plane, which over a map $T$ is conformally equivalent to $\mathbb{D}$. 
	This shows that $T\circ s\circ f_n$ forms a uniformly bounded family, so by Montel a subsequence converges to an $\tilde f:\Omega \to \overline{\mathbb{D}}.$ 
	If $f$ is not a constant function with image on the boundary of $\mathbb{D}$ we see that $s^{-1} \circ T^{-1}\circ \tilde f$ is a local uniform limit of a subsequence of $f_n$ and hence is holomorphic. 
	It also follows that it is the pointwise limit of this subsequence so by uniqueness of limits $f \equiv s^{-1}\circ T^{-1}\circ \tilde f$. 
	<br>
	Now instead suppose that $\tilde f$ is a function taking a value in $\partial \mathbb{D}$. 
	We immediately note that since the image of $\tilde f$ is contained in $\overline{D}$ this forces $\tilde f$ to be constant by maximum modulus. 
	If this occurs away from the pole of $T^{-1}$ then the our subsequence still converges to $f =s^{-1}\circ T^{-1}\circ \tilde f$ uniformly on compact sets, and now this function is a constant map to some points of $\mathbb{R}^+.$
	If $\tilde f$ take the value of the pole of $T^{-1}$ then we note that our subsequence of $\{f_n\}_{n=1}^\infty$ is now converging uniformly to $\infty$, but this is impossible because of the sequence has a pointwise limit $f:\Omega\to\mathbb{C}$. 
</details>

Problem 8 (Prelim August 2012)
------
Prove that for any simply connected open subset of the complex plane, there exists an analytic function that cannot be analytically continued to a larger domain.
<details>
	<summary>Hint</summary>
	By Riemann mapping theorem we can take our domain to be $\mathbb{D}$. An extension of a function $f$ will certainly not exist if $f$ is unbounded on all neighborhoods of points on the boundary.
</details>
<details>
	<summary>Solution</summary>
	For this problem its handy to think of the diatic rationals between $0$ and $1$, $r= \sum_{i=1}^\infty c_i 2^{-n}$ where $c_i = 0,1$. 
	Note that for a diatic $r$ rational whose representation halts at $i = N$ we have $2^k r \in 2\mathbb{Z}$ whenever $k > N$. 
	This immediately can be used to define a function by power series
	$$ f(z) = \sum_{n=1}^\infty z^{2^k} $$
	which has radius of convergence $1$. 
	At $z = e^{ir\pi}$ we see 
	$$f (z) = \sum_{n=1}^\infty e^{2^k i \pi r} = \sum_{n=1}^N e^{2^k i \pi r} + \sum_{i=N+1}^\infty 1 $$
	showing that no analytic extension exists, for $f$ blows up in every neighborhood of points on the boundary of $\partial \mathbb{D}$. 
	<br>
	In the case that our set is not $\mathbb{D}$ we know there exists a Riemann map $R:U\to \mathbb{D}$ so here we just take $f\circ R$ to be our function. 
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
<details>
	<summary>Solution</summary>
	We let $T: H\to \mathbb{D}$ be a Mobius transformation then $T\circ f_n$ defines a family of bounded maps and by Montel they have subsequence that converges uniformly on compact sets to some limit $\tilde f:H\to \overline{\mathbb{D}}$. 
	We note that this limit cannot take value in $\partial D$, for then by maximum modulus the limiting function is constant hence the subsequence $f_n$ would converge pointwise to a constant function. 
	Since this limiting function is contained entirely in $\mathbb{D}$ we can apply $T^{-1}$ to it and the subsequence $T\circ f_n$ to find a subsequence of $f_n$ converging to $T^{-1}\circ \tilde f$. 
	By uniqueness of limits we see that $f \equiv T^{-1}\circ \tilde f$ hence $f$ is holomorphic by Weierstrass' theorem. <br>

	To see that $f$ is one-to-one select $w\in H$ and let $U = \{ x+iy: |x|\leq N, N^{-1} \leq y \leq N\}$. 
	We know that on the boundary of $U$
	$$ \frac{1}{2\pi i}\int_{\partial U} \frac{f_n'(z)}{f_n(z) - w}\,dz = 0\text{ or }1$$
	Now, from the work that we have done we know that as long as $w \notin f_n(\partial U)$ for all $n > N$ we can conclude
	$$\frac{1}{f_n(z) - w} \to \frac{1}{f(z) - w}$$
	uniformly on compact sets. 
	By the integral formula we also find that 
	$$ f'_n(z) = \int_U \frac{f_n(\xi)}{(z-\xi)^2}\,d\xi \to \int_U\frac{f_n(\xi)}{(z-\xi)^2}\,d\xi = f'(z)$$
	uniformly on compact sets. 
	Since $\partial U$ is compact, we can commute limits an integrals by uniform convergence
	$$ 0\text{ or } 1 = \frac{1}{2\pi i}\int_{\partial U} \frac{f_n'(z)}{f_n(z) - w}\,dz \to \frac{1}{2\pi i}\int_{\partial U} \frac{f'(z)}{f(z) - w}\,dz $$
	hence $f$ is injective on $U$. 
	Since we could take $N$ as large as we want, we can conclude $f$ is one-to-one over all of $H$. 
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
<details>
	<summary>Solution</summary>
	Proceeding as we did in problem 7 (except now selecting a branch of square root that excludes $\mathbb{R}^{-}$) we see $T\circ s \circ f_n$ defines a family of bounded functions and hence a subsequence converges to some $\tilde f:\mathbb{D} \to \overline{\mathbb{D}}$. 
	We clearly see that these functions do not take value on the boundary (for then by maximum modulus $\tilde f$ is constant, however $(T\circ s \circ f_n)(0) = 0$ for all $n$.)
	Hence the range of $\tilde f$ is contained in $\mathbb{D}$ so $s^{-1}\circ T^{-1}\circ \tilde f$ is holomorphic and the uniform limit on compact sets of the corresponding subsequence of $f_n.$ <br>

	If we remove the assumption that $f_n(0) = 1$ it is possible our sequence of functions blow up uniformly to infinity. Take, for instance, $f_n:\mathbb{D} \to U$ mapping $z \mapsto z+1+n$ which obviously converges uniformly to $\infty.$ 
	Our composition $T\circ s\circ f_n$ then has all subsequences converging uniformly to a constant function taking value the pole of $T^{-1}$. 
</details>

Problem 11 (Prelim August 2009)
------
Let $\mathcal{F}$ be the set of all holomorphic functions $f$ on $\mathbb{D}$ such that $$ \int_\mathbb{D} |f(x + iy)|^2dx\,dy \leq 1 $$ show that $\mathcal{F}$ is a normal family.
<details>
	<summary>Hint</summary>
	Selecting any disk of radius $r < 1$ apply the mean value property to get a bound on $|f(z)|$ over this domain. To finish, look for variations of Montel's theorem or find an appropriate diagonal argument. 
</details>
<details>
	<summary>Solution</summary>
	Selecting $0 < r < 1$ let $D = \{z: |z| \leq r\}$. The mean value property tells us that
	$$ |f(z)|^2 \leq \frac{1}{\pi (1-r)^2} \int_{D} |f(z)|^2\,dz \leq \frac{1}{\pi(1-r)^2}$$
	This shows that $f$ is locally uniformly bounded on $\mathbb{D}$ hence Montel's theorem tells us $\mathcal{F}$ is a normal family. 
</details>
