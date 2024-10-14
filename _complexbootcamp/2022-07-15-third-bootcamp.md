---
title: 'Complex Bootcamp Exercises: Integration I'
date: 2022-07-15
permalink: /complex-prelim-bootcamp/2022/07/bootcamp-2022-ex-3/
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
Suppose $D = \\{z:|z-a| \leq r\\}$ for $a\in \mathbb{C}$ and $r > 0$. 
For $f$ holomorphic in a neighborhood of $D$ prove the mean value property $$ f(a) = \frac{1}{2\pi} \int_{0}^{2\pi} f(a + re^{i\theta})\,d\theta. $$
<details>
	<summary>Hint</summary>
	Consider writing $f(a)$ in terms of Cauchy's integral formula.
</details>
<details>
	<summary>Solution</summary>
	Using the integral formula on the circle $|z-a| = r$ to evaluate $f(a)$ we find
	$$ \begin{align*}
		f(a) &= \frac{1}{2\pi i}\int_{|z-a| = r} \frac{f(z)}{z - a}\,dz \\
		&= \frac{1}{2\pi i} \int_0^{2\pi} \frac{f(a+re^{i\theta})}{re^{i\theta}} ire^{i\theta}\,d\theta \\
		&= \frac{1}{2\pi} \int_0^{2\pi} f(a + re^{i\theta})\,d\theta
	\end{align*} $$
</details>

Problem 2 (Prelim August 2020)
------
Is there an entire function $f$ such that $|f(z)| \geq e^{|z|}$ for all $|z| > R >0$? Either provide an example or prove none exists. 
<details>
	<summary>Solution</summary>
	Instinctively you may want to say "$|1/f(z)| \leq e^{-|z|} \leq 1$" and conclude $f$ is constant by Liouville, but this won't work since we only know our bound for $|z|$ large. 
	Instead define $g(z) = 1/(f(1/z))$. Then we find 
	$$ |g^{(n)}(0)| \leq \frac{n!}{2\pi} \int_0^{2\pi} \left| \frac{g(re^{i\theta})}{(re^{i\theta})^n} \right|\,d\theta \leq C \frac{e^{-1/r}}{r^n} \to 0 $$
	as $r\to 0$. 
	Having all derivatives zero is equivalent to $g$ being identically zero, which is impossible. 
	Hence no such $f$ exists. 
</details>

Problem 3 (Prelim August 2009)
------
Let $f$ be a non-constant entire function. Assume there are two complex numbers $a_1, a_2 \ne 0$ such that $$ f(z+a_1) = f(z+a_2) = f(z).$$
Show that $a_1/a_2 \in \mathbb{Q}$. 
<details>
	<summary>Hint</summary>
	Consider the cases $a_1/a_2 \notin \mathbb{R}$ and $a_1/a_2 \in \mathbb{R}$ separately. 
</details>
<details>
	<summary>Solution</summary>
	In the case that $a_1/a_2 \notin \mathbb{R}$ we see that $a_1,a_2$ point in different directions. 
	We can consider the parallelogram with vertices $0, a_1, a_2, a_1+a_2$. 
	The region bounded by this parallelogram is compact, hence $f$ is bounded on this set. 
	We can then tile $\mathbb{C}$ by copies of this parallelogram shifted by $na_1 + ma_2$, $m,n\in\mathbb{Z}$ and by periodicity it follows that our bound on the first parallelogram holds on all of $\mathbb{C}$. 
	Hence by Liouville's theorem $f$ is constant. <br>

	Now suppose that $\lambda = a_1/a_2  \in \mathbb{R} \setminus \mathbb{Q}$. 
	If we let $A = \{ n \lambda + m|m,n\in \mathbb{Z}\}$ we note that $A$ cannot have any accumulation points, for this would allow us to apply the identity theorem to $f$ on a convergent sequence of periods. 
	Hence there exists $r = \text{min} A \cap \{x > 0\}$ which is attained by some $r = n\lambda + m$. 
	We claim $A =r\mathbb{Z}$. 
	Indeed, if $q \in A \setminus r\mathbb{Z}$ (and WLOG $q > 0$) then there exists an integer $k$ such that $kr < q < (k+1)r$, which is equivalent to $0 < q - kr < r$. 
	But note that $q -kr \in A$ since $A$ is an ideal, which contradicts that $r$ was the minimal positive element of $A$. 
	Now since $1 \in A$ we can write $kr = 1$ for some $k \in \mathbb{Z}$ hence $r \in \mathbb{Q}$ and $a_1/a_1 = (r-m)/n \in \mathbb{Q}$. 
</details>

Problem 4 (Prelim January 2008)
------
Suppose that $f$ is entire. Show that $$ \lim_{|z| \to \infty} |f(z)| = \infty \iff f\text{ is a polynomial.} $$
<details>
	<summary>Hint</summary>
	Examine the singularity at infinity. 
</details>
<details>
	<summary>Solution</summary>
	We can immediately conclude that the singularity at infinity is not an essential singularity. 
	This leaves that it is a pole of some order $n \in \mathbb{N}$. 
	In particular, $$ \lim_{z\in \infty} \frac{f(z)}{z^n} = c \ne 0.$$
	We can then conclude that if we select an $M > |c|$ that $$ |f(z)| \leq M|z|^n$$ for $|z|$ large enough. 
	Note by the integral formula that $$|f^{(k)}(0)| \leq \frac{k!}{2\pi} \int_{|z|=R} \left| \frac{f(z)}{z^{k+1}} \right| \,dz \leq \frac{k!}{2\pi} \int_{|z| = R} \frac{M|z|^n}{|z|^{k+1}} \,dz$$
	where are last inequality holds for $R$ suitably large. 
	In the case of $k > n$ we take the limit as $R\to \infty$ and find $f^{k}(0) = 0$. 
	Hence at zero $f$'s Taylor expansion is the polynomial $$f(z) = f(0) + f'(0)z + \cdots + \frac{f^{(n)}(0)}{n!} z^n.$$
	This series has infinite radius of convergence, hence it is equal to $f$ for all $z \in \mathbb{C}$. 
</details>


Problem 5 (Prelim August 1994)
------
Prove that all conformal self maps of $\mathbb{C}$ are affine transformations. 
<details>
	<summary>Hint</summary>
	What order can the pole at infinity be? What happens if $f'(z) = 0$ for some $z$?
</details>
<details>
	<summary>Solution</summary>
	First note that if such a map is a polynomial, it must be of degree $1$ for a degree $n$ polynomial gives an $n$ to $1$ map (counting repeated roots.)
	Now, if a conformal self map of $\mathbb{C}$ is not a polynomial the contrapositive of 4 tells us the limiit $$\lim_{z\to \infty} f(z)$$ does not exist (or in other words, the singularity at $\infty$ is essential.)
	As a result, $f(\{z: |z| > 2\})$ must be dense subset of $\mathbb{C}$ as it contains a neighborhood of $\infty$. 
	However, by the open mapping theorem $f(\{z: |z| < 1\})$ is an open subset of $\mathbb{C}$ and hence has a nontrivial intersection with $f(\{z:|z| > 1\})$. 
	Since the preimage sets are disjoint this clearly violates injectivity, ruling out the possibility for a non-polynomial self map. 
</details>

Problem 6 (Prelim January 2019)
------
Assume $f$ is meromorphic on $\mathbb{C}$ and that it is bounded outside some compact set. 
Show that $f$ must be a rational function. 
<details>
	<summary>Hint</summary>
	How many poles can $f$ have? Can you define $g(z) = f(z)\prod (z-z_i)^{m_i}$ and get a corresponding bound on $g$? 
</details>
<details>
	<summary>Solution</summary>
	Let $K$ be the compact set outside of which $f$ is bounded. 
	If $S$ is the set of poles of $f$ then note that $S$ cannot have an accumulation point as all singularities are isolated. 
	Since $K$ is compact it then must follow that $S$ is finite, let $S = \{z_i\}_{i=1}^n$ and let each pole have corresponding order $m_i$. 
	Then we can define $$g(z) = f(z) \prod_{i=1}^n (z-z_i)^{m_i}$$
	and by hypothesis we find that off our set $K$ we have a bound $|g(z)| \leq M \prod_{i=1}^n (z-z_i)^{m_i}$. 
	Repeating the analysis done in problem 4 we can then reveal that $g$'s Taylor expansion at $0$ is a polynomial and by definition of $g$ we see that $f$ is rational. 
</details>

Problem 7 (Prelim August 2002)
------
Let $F$ be a finite subset of $\mathbb{C}$ and let $D = \mathbb{C}\setminus F$. 
Suppose $f$ is a non-constant analytic function on $D$. Prove that $f(D)$ is dense in $\mathbb{C}$. 
<details>
	<summary>Hint</summary>
	If $f(D)$ is not dense then we can construct $g(z) = (f(z)-z_0)^{-1}$ where $z_0 \in \mathbb{C} \setminus \overline{f(D)}$. 
</details>
<details>
	<summary>Solution</summary>
	Following the hint, we can find $z_0 \notin \overline{f(D)}$ such that $|z_0 - z| > r > 0$ for all $z \in f(D)$. 
	Then $|g(z)| = |f(z) - z_0|^{-1} \leq r^{-1}$, hence at each pole of $f$ $g$ has a removable singularity and hence we can extend $g$ to an entire function. 
	By Liouville's theorem it follows that $g$ is constant, and hence so is $f$. 
</details>

Problem 8 (Prelim August 2016)
------
Let $f$ be holomorphic on a connected open neighborhood of $\mathbb{D}$. Assume that $|f(z)| = |z+1|$ for all $|z| = 1$, $f(1) = 2$, and $f$ has simple zeros at $\pm i/2$ and no other zeros in $\mathbb{D}$.
Show that these properties determine $f$ uniquely. Calculate $f(0)$.
<details>
	<summary>Hint</summary>
	Consider $g(z) = f(z)/(z+1)$. 
</details>
<details>
	<summary>Solution</summary>
	Following the hint we first note that since $f(-1) = 0$ the singularity that $g$ has at $z = -1$ is removable. 
	Additionally, for all other values of $z$ with $|z| = 1$ we see $|g(z)| = 1$ hence whatever value the removable singularity has must satisfy $|g(-1)| = 1$ by continuity. 
	Hence the image of $g$ is contained in the disk. 
	Next, we define $T_1,T_2:\mathbb{D} \to \mathbb{D}$ as Möbius transformations fixing the disk with zeros $i/2,-i/2$ respectively. 
	$$ T_1(z) = \frac{z- i/2}{1-iz/2} \text{ and } T_2(z) = \frac{z + i/2}{1 + iz/2} $$
	Then $h(z):= g(z)/(T_1(z)T_2(z))$ has isolated singularities at $\pm i/2$, but since both $g$ and $T_i$ have simple roots at these values the singularities are removable. 
	Hence this $h$ can be extended to all of $\mathbb{D}$ and since $|T_i(z)| = 1$ when $|z| = 1$ we see its image is within $\mathbb{D}$ due to the maximum modulus principle. 
	By hypothesis we now have that $h$ is nonzero for all $z\in \mathbb{D}$, allowing us to apply the minimum modulus principle and deduce that $1 \leq |h(z)| \leq 1$ on the disk, hence $h$ is constant. 
	Since $$h(1) = \frac{f(1)}{2T_1(1)T_2(1)} = 1$$ we arrive at $$f(0) = -\frac{i}{2}\cdot \frac{i}{2} = \frac{1}{4}.$$
</details>


Problem 9 (Prelim January 2014)
------
Let $f$ be an entire function and define $M(r) =\max_{|z| = r} |f(z)|$. Show $M$ is continuous on $[0,\infty)$. 
<details>
	<summary>Solution</summary>
	If $f$ is constant then $M$ is constant as well and trivially continuous.
	If $f$ is non-constant then by maximum modulus $M(r) < M(s)$ for all $0 \leq r < s$. 
	Fixing $s$ we note that it is impossible for $$\lim_{r\to s^{-}} M(r) < M(s),$$ because the limit exists due to the monotone convergence theorem and  the maximum modulus principle tells us that $M(s) = \max_{z\in B_s(0)} |f(z)|$. 
	Likewise we cannot have $$ \lim_{r\to s^{+}} M(r) > M(s)$$, for if this were true we could select a sequence $\{z_n\}_{n=1}^\infty$ such that $|z_n| = s + 1/n$ and $|f(z_n)| = M(s+1/n)$. 
	Since this sequence is contained in a bounded region it is precompact with limit point $z$ on the circle of radius $s$.
	By continuity, we see $$M(s) \geq |f(z)| = \lim_{n\to \infty} |f(z_n)| = \lim_{n\to \infty} M(s+1/n) \geq M(s).$$
</details>

Problem 10 (Prelim January 1997)
------
Suppose that $f$ is analytic on the disk $|z| < 2$ except for a simple pole at $z = 1$ with residue $A$. 
Show that \[ \lim_{n\to\infty} \frac{f^{(n)}(0)}{n!} = - A. \]
<details>
	<summary>Hint</summary>
	Consider $g(z) := f(z) - A/(z-1)$ and try extend it to $z = 1$. 
	What is its Taylor expansion?
</details>
<details>
	<summary>Solution</summary>
	Following the hint, $g$ has a removable singularity at $z = 1$ so we can analytically extend its domain to include $z = 1$. 
	Note that the Taylor series of $-A/(z-1) = A(1 + z + z^2 + \cdots + z^n + \cdots)$. 
	Hence the Taylor series for $g$ is 
	$$ g(z) = \sum_{n=0}^\infty \left(\frac{f^{(n)}(0)}{n!} + A\right)z^n.$$
	Since $g$ is holomorphic on the disk $|z| < 2$ and we made this expansion at $z = 0$ it has a radius of convergence of at least $2$. 
	In particular, we see the series converges for $z = 1$ hence as $n\to \infty$ the summands converge to zero which yields us the desired statement $$ \lim_{n\to\infty} \frac{f^{(n)}(0)}{n!} = -A.$$
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
<details>
	<summary>Solution</summary>
	Fixing $x,y_1 \in \mathbb{R}$ the map $[y_0,y_1] \to \mathbb{C}$ given by $y\mapsto f(x+iy)$ is differentiable with $|(\partial/\partial y) f(x+iy)| \leq |f'(x+iy)|$. 
	By the mean value theorem we can bound $$|f(x+iy_1)-f(x+iy_0)| \leq |y_1 - y_0| \sup_{y \in [y_0,y_1]} |f'(x+iy)|.$$
	Next we note that we can bound $f'$, since for all $r < x$ 
	$$|f'(x+iy)| \leq \frac{1}{2\pi} \int_{|z-(x+iy)| = r} \left|\frac{f(z)}{(z-(x+iy))^2} \right|\,dz = \frac{1}{2\pi}\frac{2\pi M r}{r^2} = \frac{M}{r}$$
	where $M$ is our bound on $f$. 
	Taking the limit as $r\to x$ we find $|f'(x+iy) | \leq M/x$. 
	Finally, taking the limit as $x\to \infty$ of our bound on $|f(x+iy_1) - f(x+iy_0)|$ we see the right hand side converges to $0$.
	Since $f(x+iy_0) \to L$ as $x\to \infty$ it follows that $f(x+iy_1) \to L$ as well. 
</details>

Problem 12 (Prelim January 2022)
------
Let $f$ be holomorphic and bounded on the upper half plane $H = \\{z: \text{Im } z > 0\\}$. 
Suppose $f(z) = f(z+1)$ for all $z\in H$. Prove that $f(z)$ has a limit as $\text{Im }z \to \infty$. 
<details>
	<summary>Hint</summary>
	Consider restricting the function to just one period $P = \{x + iy: 0\leq x < 1, 0 < y\}$. Can conformal maps simplify the problem?
</details>
<details>
	<summary>Solution</summary>
	Consider the restriction of the multivalued map $\log:\mathbb{D}\setminus\{0\} \to \{z: \text{Re }z < 0\}$ which sends $re^{i\theta} \mapsto \log(r) + i(\theta + 2\pi k), k\in \mathbb{Z}$. 
	Multiplying by a factor of $-i/(2\pi)$ we see the image rotates onto $H$ and the difference between the values of $-i \log(z)/(2\pi)$ differ by $1$, matching the period of $f$. 
	Indeed, the map $$ h(z) = f\left( \frac{-i \log(z)}{2\pi} \right)$$ is well defined due to the periodicity of $f$ and at any $z \in \mathbb{D}\setminus \{0\}$ we can select any branch of $\log$ with domain containing $z$ to see that locally $h$ is a composition of holomorphic functions and hence is holomorphic at $z$. 
	Finally, by hypothesis $f$ is bounded hence so is $h$, therefore the singularity of $h$ at the origin is removable. 
	Now we note that taking the limit as $x \to \infty$ of $f(x+ iy)$ corresponds to the limits $|z| \to 0$ of $h(z)$ hence the prior limit exists and is equal to $h(0)$. 
</details>

Problem 13 (Prelim August 2014)
------
Suppose $f$ is meromorphic on $\mathbb{D}\setminus\\{0\\}$ having poles at $z = 1/2,1/3,1/4,\dots$ Show that for every $r > 0$ the restriction of $f$ to $0 < |z| < r$ has dense image in $\mathbb{C}$. 
<details>
	<summary>Hint</summary>
	Suppose not - then we can construct $g(z) = (f(z) - w)^{-1}$ where $w \notin \overline{f(B_r(0)\setminus\{0\})}$. 
</details>
<details>
	<summary>Solution</summary>
	Following the hint, for $r$ suitably small we select $w\notin \overline{f(B_r(0)\setminus \{0\})}$ giving the existence of an $s > 0$ such that $|w - z| > s$ for all $z \in \overline{f(B_r(0)\setminus\{0\})}$. 
	It then follows that $|g(z)| = |f(z) - w|^{-1} < s^{-1}$. 
	In particular, the poles of $f$ at $z = 0, 1/2, 1/3,\dots$ become removable singularities of $g$ with value $0$.
	If the singularity at zero is also removable since $g$ is bounded. 
	With this we can apply the identity theorem and it follows that $g$ is the zero function, a contradiction. 
</details>
