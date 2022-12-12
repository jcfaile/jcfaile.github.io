---
title: 'Complex Bootcamp Exercises: Integration II'
date: 2022-07-19
permalink: /complex-prelim-bootcamp/2022/07/bootcamp-2022-ex-4/
tags:
  - bootcamp
  - complex analysis
---

This set of problems focuses on the residue theorem, argument principle, and existence of branches. Some more problems on topics from the last post are also included. 

Resources
------
Ahlfors section 4.4-4.6

Problems
======

Problem 1 (Prelim August 2015)
------
Let $f$ be a non-constant meromorphic function satisfying $$f(z) = f(z+\sqrt{2}) = f(z+i\sqrt{2})$$ and assume $f$ has at most a single pole in $\mathbb{D} = \\{z: |z| < 1 \\}$. 
<ol><li>
Show that there must exist a pole in $\mathbb{D}$. 
<details>
	<summary>Hint</summary>
	If there is no pole in $\mathbb{D}$ how many poles can $f$ have elsewhere?
</details>
<details>
	<summary>Solution</summary>
	Note that we can fit a square in side of $\mathbb{D}$ with sides parallel to the real/imaginary axes and with lengths $\sqrt{2}$. 
	If there is no pole in this square then $f$ is bounded on it. 
	However, since our periods are $\sqrt{2},i\sqrt{2}$ it would then follow that $f$ is bounded on all of $\mathbb{C}$ - hence its entire and by Liouville's theorem must be constant. 
	Therefore, there exists at least one pole in this square contained in $\mathbb{D}$. 
</details>
</li><li>
Show that this pole cannot be simple.
<details>
	<summary>Hint</summary>
	Try integrating along a square with side lengths $\sqrt{2}$. 
</details>
<details>
	<summary>Solution</summary>
	We can parameterize a path along the square from part (a) by $\gamma:[0,1] \to \mathbb{C}$ a piecewise linear function $\gamma$ <br>
	<img src="/assets/complex-ex-4/square_contour.png" class="center" alt="Square contour"><br>
	Note that due to the period, the values of $f$ along $\gamma_1$ and $\gamma_2$ are identical, however we are now traversing in the opposite direction so $\gamma_1' = -\gamma_2'$. 
	This gives us the relationship 
	$$ \begin{align*} \int_{\gamma_2} f\,dz &= \int_{0}^{1/4} \gamma'_2(t+1/2) f(\gamma_2(t+1/2))\,dt \\&= -\int_{1/4}^0 \gamma_2'(3/4-u) f(\gamma_2(3/4 - u))\,du \\&= -\int_0^{1/4} \gamma_1'(u)f(\gamma_1(u))\,du = - \int_{\gamma_1} f\,dz\end{align*}$$
	The same applies to $\gamma_3$ and $\gamma_4$. Hence, if our pole lies at $z_0 \in \mathbb{D}$, we find
	$$ 2\pi i\text{res}(f,z_0) = \int_\gamma f\,dz = 0 $$
	allowing us to conclude that the pole at $z_0$ is not simple. 
</details>
</li></ol>

Problem 2 (Prelim January 1997)
------
Suppose that $f$ is a holomorphic function on a neighborhood of $\overline{\mathbb{D}}$ and on $\partial \mathbb{D}$ $f$ satisfies $|f(z)| \leq a$ when $\text{Im}(z) \geq 0$ and $|f(z)| \leq b$ when $\text{Im}(z) \leq 0$. Show that
\[ |f(0)| \leq \left(ab\right)^{1/2}. \]
<details>
	<summary>Hint</summary>
	Consider both $f(z)$ and $f(-z)$. 
</details>
<details>
	<summary>Solution</summary>
	Defining $g(z) =f(z)f(-z)$ we find that $|g(z)| \leq ab$ on the boundary of the disk, hence by maximum modulus we see that $|g(0)| = |f(0)|^2 \leq ab$. 
</details>

Problem 3 (Prelim August 1996)
------
Suppose $f$ is analytic on an open neighborhood of $\overline{\mathbb{D}}$ and that it is injective on $|z| = 1$. 
Show that $f$ is injective on $\mathbb{D}$. 
<details>
		<summary>Hint</summary>
	Apply the Jordan curve theorem. What can you deduce about solutions to $f(z) = w$ for arbitrary $w\in \mathbb{C}$? 
</details>
<details>
	<summary>Solution</summary>
	Let $\gamma:[0,1] \to \partial \mathbb{D}$ be a parameterization of the unit circle. 
	Since $f$ is injective we see that $f\circ \gamma$ is a simple closed curve, and by the Jordan curve theorem we see that $\mathbb{C}\setminus f\circ \gamma([0,1])$ has the two connected components $$ \begin{align*} U &= \{ z: n(f\circ \gamma,z) = 0 \} \\ V&= \{z:n(f\circ \gamma,z) = \pm 1\end{align*}\}$$
	where the $\pm 1$ just depends on orientation. 
	Using the argument principle we find that the number of solutions to $f(z) = w$ is $$ \frac{1}{2\pi i} \int_{\gamma} \frac{f'(z)}{f(z) - w}\,dz = \frac{1}{2\pi i} \int_{f\circ \gamma} \frac{1}{z-w}\,dz = n(f\circ \gamma,w) = 0\text{ or } \pm 1$$
	hence $f(z) = w$ has at most one solution so $f$ must be injective.
</details>

Problem 4 (Prelim January 2022)
------
Let $K$ be a compact connected subset of $\mathbb{C}$ containing $\pm i$. 
Show that there exists a holomorphic branch of $(z^2 + 1)^{-1/2}$ in $\mathbb{C} \setminus K$ and determine the possible values of its integral along closed curves in $\mathbb{C} \setminus K$. 
<details>
	<summary>Hint</summary>
	Recall that a branch of $\log f$ exists for a function $f$ on a domain $U$ if and only if $\int_\gamma f'/f\,dz = 0$ for all closed curves $\gamma:S^1\to U$. 
	If this this integral is nonzero, consider defining a multivalued primitive and composing with $e^z$, if the values differ by multiples of $2\pi i$ the composition is a single valued function. 
</details>
<details>
	<summary>Solution</summary>
	Letting $f(z) = (z^2 + 1)^{-1/2}$ we can compute that $$ \frac{f'(z)}{f(z)} = -\frac{z}{z^2 + 1} $$
	which has poles of order $2$ at $\pm i$. 
	We then compute 
	$$\text{res}_{z= i}\left( \frac{f'}{f}\right) = \lim_{z\to i} -(z-i) \frac{z}{(z^2 + 1)^2} = -\frac{i}{2i} = -\frac{1}{2} $$
	and performing the same computation at $z = -i$ we find 
	$$ \text{res}_{z = -i}\left(\frac{f'}{f}\right) = -\frac{1}{2} = \text{res}_{z = i}\left(\frac{f'}{f}\right) $$
	as well. 
	Finally, if $\gamma$ is a closed curve in $\mathbb{C}\setminus K$ the residue theorem gives us that 
	$$ \int_\gamma \frac{f'}{f}\,dz = -i\pi (n(\gamma, i) + n(\gamma, -i)). $$
	We now note that $n(\gamma,i) = n(\gamma,-i)$ for any such curve divides $\mathbb{C} \setminus \gamma(I)$ into connected components with identical index. 
	Therefore, 
	$$ \int_\gamma \frac{f'}{f}\,dz = -2i\pi k $$
	for $k\in \mathbb{Z}$. 
	In general, we know that a logarithm of a function $f$ exists when this integral is zero for all closed curves $\gamma$ so we are not fortunate enough to arrive at a branch fo $\log(f)$. 
	However, since the integral over closed $\gamma$ is always a multiple of $2\pi i$ we see that it matches the period of $\text{exp}$. 
	As a result, we can define a multivalued map $h:\mathbb{C} \setminus K \to \mathbb{C}$ by fixing some $z_0 \in \mathbb{C}\setminus K$ and letting $l = \log f(z_0)$ for any branch of $\log$ and $\sqrt{}$ with appropraite domains. Then
	$$ h(\xi) = \left\{ l + \int_{\gamma} \frac{f'}{f}\,dz: \gamma: [0,1], \gamma(0) = z_0, \gamma(1) = \xi \right\}.$$
	(Note that this is assuming that there is just one connected component in $\mathbb{C} \setminus K$. This is not necessarily true, but we can define $h$ on other components by fixing other $z_0$ in that component and working piecewise.)
	From prior work we see the values of $h(\xi)$ all differ by multiples of $2\pi i$ hence $z \mapsto \exp(h(z))$ is a well defined function. 
	We can also see that this function is holomorphic, for if we select any $z$ in the domain there exists a simply connected neighborhood $U$ of $z$ for which $$ \int_\gamma \frac{f'}{f}\,dz = 0$$ for all closed curves $\gamma:[0,1]\to U$. 
	Hence we can locally define a holomorphic branch $l$ of $\log f$ on this domain and in $U$ $\text{exp}(h(z)) = \text{exp}(l(z))$ showing the left hand side is indeed holomorhpic at $z$. <br>
	Finally, we must show that $\text{exp}(h(z))$ is indeed a branch of $f$. 
	Differentiating $\text{exp}(2h(z))/(f(z))^2$ we find 
	$$ 
	\begin{align*}
		\frac{d}{dz} \text{exp}(2h(z))(z^2 + 1) &= h'(z)\text{exp}(2h(z))f(z) + 2z \text{exp}(2h(z)) \\
		&= 2\text{exp}(2h(z)) \left[ \frac{-z}{z^2 + 1} + \frac{z}{z^2 + 1}\right] = 0 
	\end{align*} 
	$$
	showing that the functions are multiples of one another. Finally, evaluating at $z_0$ we see $\text{exp}(h(z_0)) = \text{exp}(l) = f(z_0)$ hence they are identical. 

	<br>
	To compute the integral of this branch over a closed curve first note that any such curve $\gamma$ can be replaced by a curve on a circle of radius $> R$ with the same integral (due to Cauchy's theorem.)
	We can let $R$ be greater the largest modulus attained on $K$. 
	Then note our branch restricted to $\mathbb{C} \setminus \overline{B_r(0)}$ can be continued analytically to $\mathbb{C}\setminus [-i,i]$. 
	Finally, we can construct a dumbbell contour along the segment $[-i,i]$ like so <br>
	<img src="/assets/complex-ex-4/dumbbell_contour.png" class="center" alt="Dumbbell contour"><br>
	On this contour we first note that as we shrink the dumbbell the contribution from the circular regions goes to zero. 
	Indeed, at $i$ we can let $\gamma(\theta) = re^{i\theta} + i$, then $|(\gamma(\theta)^2 + 1)^{-1/2}| \leq [r(2-r)]^{-1/2}$ after factoring.
	Then by the ML-lemma we find that 
	$$ \begin{align*}
		\left| \int_\gamma \sqrt{z^2 + 1} \, dz \right| &\leq L(\gamma)[r(2-r)]^{-1/2} \\
		&= 2\pi \frac{\sqrt{r}}{\sqrt{2-r}} \to 0
	\end{align*} $$
	as $r\to 0$. 
	This shows that integrating along a simple closed circle of radius $> 1$ is equivalent to integrating up and down the segment $[-i,i]$, however when we swap directions we hop over our branch cut so the values will be negated.
	This negation is justified by the integral of $f'/f$ along any small circle around $\pm i$, which we know gives $\pm \pi i$ so apon exponetiating we will find the accross the branch cut our brach differs by a factor of $e^{i\pi}$. 
	Integrating in one direction we find 
	$$ \int_{[-i,i]} \frac{1}{\sqrt{1+z^2}}\,dz = \int_{-1}^1 \frac{i}{\sqrt{1-t^2}}\,dt = \pm \pi i $$
	hence the integral over any closed curve will be an integer multiple of $2\pi i$. 
</details>

Problem 5 (Prelim August 2020)
------
Assume $f:\mathbb{C}\setminus \overline{\mathbb{D}} \to \mathbb{D}$ is holomorphic. Prove that $|f'(2)| \leq 1/3$.
<details>
	<summary>Hint 1</summary>
	Precompose with $1/z$ and note the singularity at zero is removable to make this a map $\mathbb{D}\to \mathbb{D}$.
</details>
<details>
	<summary>Hint 2</summary>
	Use a Mobius transformation on the disk that maps $1/2 \mapsto 0$. 
	Then the Schwarz inequality gives a bound on the derivative at zero. 
	This related to the "Schwarz-Pick" theorem and its very handy have memorized. 
</details>
<details>
	<summary>Solution</summary>
	Define $g:\mathbb{D} \to \mathbb{D}$ as $g(z) = f(z^{-1})$ for $z \ne 0$ and at $z = 0$ the singularity is removable, so just define $g(0)$ to be the limit. 
	Then to estimate $f'(2)$ we will first estimate $g'(1/2)$.
	The Schwarz-Pick theorem states that 
	$$ \left| \frac{ g(z_1) - g(z_2) }{1-\overline{g(z_1)} g(z_2) } \right| \leq \left| \frac{z_1 - z_2 }{1-\overline{z_1} z_2 } \right| $$
	Swapping the denominator on the left and the numerator on the right we see the left hand side becomes the difference quotient between the points $z_1,z_2$. 
	Letting both of these values approach an arbitrary $z \in \mathbb{D}$ we find
	$$ |g'(z)| \leq \frac{1 - |g(z)|^2}{1 - |z|^2}$$
	which leads us to 
	$$ \left| -f'(2)\left(\frac{1}{2}\right)^{-2} \right| = \left| g'\left( \frac{1}{2}\right)\right| \leq \frac{1-|g(1/2)|}{1-(1/2)^2} \leq \frac{4}{3} $$
	giving the desired bound. 
</details> 

Problem 6 (Prelim August 2020)
------
Suppose that $f$ is analytic on $\mathbb{D}$ and satisfies $|f(z)| \leq M$ for all $z\in \mathbb{D}$. Assume further that $f$ vanishes at the points $ \\{z_j\\}_{j=1}^N $ where $1 \leq N \leq \infty$.)
Prove that 
<p> $$ |f(z)| \leq M \left| \prod_{j=1}^m \frac{z-z_j}{1-\overline{z_j}z} \right|\quad \forall z\in\mathbb{D} $$ </p>
for any $1 \leq m \leq N$ (or if $N = \infty$ then $1 \leq m < N$. )
<details>
	<summary>Hint</summary>
	Consider the function $$ g(z) = \frac{f(z)}{\prod_{j=1}^m \frac{z-z_j}{1-\overline{z_j}z} }. $$ Are its singularities removable? What is $|g|$ as you approach $\partial \mathbb{D}$?
</details>
<details>
	<summary>Solution</summary>
	As discussed in the conformal mapping section, maps of the form $$ z\mapsto \frac{z-a}{1-\overline{a}z}$$ fix the disk and have a single simple root at $z = a$. 
	As a result of this, the singularities of $g$ introduced by the roots $z_j$ are removable as they are roots of $f$ of the same or higher order. 
	Additionally on the boundary these fractional transformations have norm $1$ while $|f| \leq M$ as we approach the boundary. 
	It follows that $g$ is bounded by $M$ on the boundary of $\mathbb{D}$ and hence by max modulus we have 
	$$ |g(z)| = \left|\frac{f(z)}{\prod_{j=1}^m \frac{z-z_j}{1-\overline{z_j}z} } \right| \leq M$$
	and multiplying over by the fractional transformations gives the desired bound. 

	<br> _Note: this is actually part (a) of a two part problem. The second part will be in a later list._
</details>

Problem 7 (Prelim January 2019)
------
Given $z\in \mathbb{C}$ and a closed curve in $\mathbb{C}\setminus \\{z\\}$ denote $n(\gamma,z)$ the index or winding number of $\gamma$ about $z$. 
If $\gamma$ can be written as \[ \gamma(t) = \sum_{k = -N}^{N} c_ke^{ikt} \]
with $c_{-N}$ and $c_N$ not both zero show that $-N \leq n(\gamma, z) \leq N$. 
<details>
	<summary>Hint</summary>
	Can you relate this integral to an application of the argument principle on a suitable function?
</details>
<details>
	<summary>Solution</summary>
	If we let $\phi:[0,2\pi] \to \mathbb{C}$ be $\phi(\theta ) = e^{i\theta}$ and $R(z) = \sum_{k=-N}^N c_kz^k$ then $\gamma = R\circ \phi$ and
	$$ \begin{align*} 
		2\pi i n(\gamma, z) &= \int_\gamma \frac{1}{\xi - z}\,d\xi \\
		&= \int_\phi \frac{R'(\xi)}{R(\xi) - z} \,d\xi
	\end{align*} $$
	which, by the argument principle, is the sum of the orders of the roots and poles of $R(\xi) - z$ contained within $\mathbb{D}$. 
	Note that $\xi^N(R(\xi) - z)$ is a polynomial of degree $2N$ and hence has between $0$ and $2N$ roots within $\mathbb{D}$. 
	Now, comparing this to $R(\xi) - z)$ we have increased the order of the root at zero by $N$. 
	So, we have over counted by $N$ and hence $$ -N \leq n(\gamma, z) \leq N $$

</details>

Problem 8 (Prelim January 2017)
------
Prove that the range of the entire function $z\mapsto z^2 + \cos(z)$ is all of $\mathbb{C}$
<details>
	<summary>Hint</summary>
	Picard's theorem tells us that this functions range can exclude at most one value. Use this to deduce that if this value exists it is in $\mathbb{R}$ then apply Rouche's theorem to show it does not exist. 
</details> 
<details>
	<summary>Solution</summary>
	If the map is not surjective suppose that it never attains $w \in \mathbb{C}$. 
	If $w \notin \mathbb{R}$ note that by Picard's theorem there is some $z$ such that $z^2 + \cos(z) = \overline {w}$ and since $\cos z$'s Taylor series has all real coefficients we have $$ w = \overline{z^2 + \cos(z)} = \overline{z}^2 + \cos(\overline{z})$$ a contradiction, hence if $w$ exists we have $w \in \mathbb{R}$. <br>

	By some simple calculus we can find that the minimum of $z^2+\cos(z)$ on $\mathbb{R}$ is $1$, hence $w < 1$. 
	For the remaining cases we can use symmetric Rouche's theorem on the functions $f(z) = z^2 + \cos(z) - w$ and $g(z) = \cos(z) - w$ to show both have the same number of roots in $\mathbb{C}$, and since $\cos$ is surjective this will complete the proof. <br>
	To do this, define the path $\Lambda = \partial \{x + i y: |x| < 2n\pi, |y| < n\}$. 
	On horizontal segments we note that $$|cos(z) - w| \geq \left| \frac{e^{\pm n} + e^{\mp n}}{2} - w \right| \geq \frac{1}{2} e^n - |w| $$
	while $|f(z) - g(z)| = |z^2| = 4\pi^2n^2 + n^2$, hence if we take $n$ suitably large we find $$|f(z) - g(z)| < |f(z)| + |g(z)|$$ on the horizontal sides of $\Lambda$. 
	On the vertical sides we note that $\cos(\pm 2\pi n + iy) = (e^y+e^{-y})/2 \geq 1 > w$, so $g(z) > 0$. 
	The triangle inequality yields $|z^2| \leq |z^2 + \cos(z) - w| + |\cos(z) -w|$, and we know equality occurs if and only if both $f$ and $-g$ point in the same direction at $z$. 
	Since $\cos(z) - w  > 0 $ we see that for equality to occur must require $z^2 \in \mathbb{R}$ which can only occur if $z\in \mathbb{R}$ or $i\mathbb{R}$. 
	The only points on the vertical edges satisfying this condition are $\pm 2n \pi$, but at these points we find 
	$$ |4n^2 \pi^2| <| 4n^2 \pi^2 + 1 - w| + |1-w| $$
	hence showing $|f-g| < |f|+|g|$ on $\Lambda$. 
	Finally, since $z\mapsto \cos z$ is surjective it follows $z\mapsto z^2 + \cos z$ is a surjective as well.
	<br> <i>The main part of the argument using Rouche's theorem is modified from <a href="https://math.stackexchange.com/q/1300356">this answer</a>.</i>
</details>

Problem 9 (Prelim January 2011)
------
Let $f$ be analytic in an anulus $ U = \\{z: r < |z| < R\\}$ where $0 < r < R$. 
Assume $f$ has no zeros in $U$. Show there exists an integer $n$ and a holomorphic function $g:U\to \mathbb{C}$ such that $f(z) = z^n e^{g(z)}$
<details>
	<summary>Hint</summary>
	What conditions must $f$ satisfy for this to be true with $n = 0$? If $\gamma$ is a simple closed curve in $U$ then what is the index $n(f\circ \gamma,0)$? Does it depend on $\gamma$?
</details> 
<details>
	<summary>Solution</summary>
	Solving for $g$ this expression becomes $$ g(z) = \log(f(z)z^{-n})$$ so we are looking for a branch of $\log$. 
	We know that such a branch will exist if 
	$$ 0 = \int_\gamma \frac{f'(z) - n f(z)z^{-n-1}}{f(z)z^{-n}}\,dz = \int_\gamma \frac{f'(z)}{f(z)} - n\frac{z^{-n-1}}{z^{-n}}\,dz $$
	which is equivalent to $n(f\circ \gamma, 0) = n\cdot n(\gamma,0)$. 
	To define $n$ lets let $\gamma = c$ be a circle centered at $0$ contained in $U$. 
	We can note that the choice of radius does not matter, for we can connect the two circle by a "tube" and by Cauchy's theorem the integral of both choices are identical. 
	Further, for a general $\gamma$ with $k = n(\gamma,0)$ we can find a homotopy of this path to $\gamma'$, the circle repeated $k$ times then $n(f\circ \gamma,0) = n(f\circ \gamma',0) = kn(f\circ c,0) =n\cdot kn(c,0) = n\cdot n(\gamma',0) = n \cdot n(\gamma,0)$. 
	This establishes that 
	$$ 0 = \int_\gamma \frac{(f(z)z^{-n})'}{z^{-n}}\,dz $$ for our choice of $n$ therefore there exists a primitive of this function, let this primitive be $g(z)$. 
	Finally, we can verify that $$ \frac{d}{dz} e^{g(z)} \frac{z^n}{f(z)} = 0$$ and $e^{g(z_0)}z_0^n = f(z_0)$ for some $z_0 \in U$ to establish that this is indeed the desired $g$. 
</details>

Problem 10 (Prelim January 2016)
------
Show that the equation $\sin(f(z)) = z$ has a solution $f$ that is analytic on the region $U = \\{z\in \mathbb{C}:|z| < 1\text{ or }\text{Im}(z) \ne 0\\}$. 
<details>
	<summary>Hint</summary>
	Write $\sin(w)$ in terms of $e^{iw}$ and solve for it. You will need to prove the existence of branches of two functions on $U$ to produce $f$. 
</details>
<details>
	<summary>Solution</summary>
	Before we begin finding $f$, first note that if $\gamma$ is any closed curve in $U$ that $$n(\gamma,1) = n(\gamma,-1) = 0.$$
	This is because the set $\mathbb{C} \setminus \gamma(I)$ has one unbounded component with $n(\gamma,z) = 0$ for all $z$ contained in this component. 
	By definition of $U$ we see that the rays $(-\infty,-1],[1,\infty)$ are both unbounded connected sets not intersecting $\gamma$ and hence must lie entirely within this component. 
	<br>
	Fix $z \in U$, we wish to solve $$ \frac{e^{iw} - e^{-iw}}{2i} = \sin(w) = z.$$
	We see that $e^{iw}$ must solve the quadratic 
	$$ \left(e^{iw}\right)^2 -2iz\left(e^{iw} \right) - 1 = 0 $$
	which gives 
	$$ e^{iw} = \frac{2iz +\sqrt{4-4z^2}}{2} = iz + \sqrt{1-z^2}$$ for some branch of $z\mapsto \sqrt{1-z^2}$ defined on $U$. 
	To observe that such a branch exists note that its logarithmic derivative is 
	$$ - \frac{z}{1-z^2} $$ which is meromorphic with two poles at $z = \pm 1$. 
	By the above note about $n(\gamma,\pm 1) = 0$ for all $\gamma$ in $U$ the residue theorem gives us
	$$ \int_\gamma - \frac{z}{1-z^2}\,dz = 0 $$
	hence a primitive $P$ exists, and we can take our branch to be $\sqrt{1-z^2} = e^{P(z)}$, given the primitive has correct initial value. 
	<br>
	Now to fully solve the equation we must find a logarithm of $iz + \sqrt{1-z^2} = iz + e^{P(z)}$. 
	Proceeding as usual, we compute its logarithmic derivative as 
	$$ \frac{i + P'(z)e^{P(z)}}{iz + e^{P(z)}} $$
	which has poles at $z$ for which $e^{P(z)} = iz$. 
	This is equivalent to $1-z^2 = -z^2$ for any choice of our branch $e^{P(z)}$, hence the function is holomorphic in $U$ and since $U$ is simply connected this allows us to construct a primitive. 
	This primitive is then our branch of $\log(iz + \sqrt{1-z^2})$. 
	Multiplying it by $-i$ then gives the function $f$ satisfying $f(z) = w$ in $U$. 
</details>

Problem 11 (Prelim August 2016)
------
Evaluate the integrals  \[  I = \int_C \sqrt{1-z^2}\,dz \quad J = \int_{0}^\infty \frac{x\sin \pi x}{1-x^2}\,dx \] for some branch of the square root function (indicate which) and $C$ is the positively oriented circle $|z| = 2$. 
<details>
	<summary>Hint</summary>
	Note that for $I$ there are no residues, but instead branch points. <br>
	For $J$ consider integrating $$f(z) = \frac{ze^{i\pi z}}{1-z^2}$$ over a large semicircle with side on $\mathbb{R}$, closely avoiding the poles at $z = \pm 1$. 
</details>
<details>
	<summary>Solution</summary>
	For $I$ we can construct a branch of $\sqrt{1-z^2}$ defined on $\mathbb{C}\setminus [-1,1]$ mapping $i \mapsto +\sqrt{2}$. 
	From here, we could proceed identically to problem 4 using a dumbbell contour with "weights" centered at the branch points $z = \pm 1$. 
	In the limiting case as the width of tubes and circles goes to zero we arrive at the integral over $C$ being the same as $$2\int_{-1}^1 \sqrt{1-x^2}\,dx = \pi.$$
	To check this, if $\gamma_r$ is a circle of radius $r$ at centered at one of $z = \pm 1$ we find that 
	$$\left| \int_{\gamma_r} \sqrt{1-z^2} \,dz \right| \leq (2\pi r)\sup_{z\in \gamma_r} |\sqrt{1-z^2}| = C2\pi r^{3/2} \to 0$$ as $r \to 0$ by the ML inequality. 
	Next we must justify the resulting integral by looking at our function along the line $0+ir$ as $r\to 0$. 
	Along this branch cut we know that it will approach some value of $\sqrt{1-0^2}$, the branch either being on the positive or negative real axis. 
	We can see that since $i \mapsto +\sqrt{2}$ that the away from the branch cut it is $>0$, but we also know that there are no roots of $1-z^2$ in $i\mathbb{R}$, hence it remains positive for all $r > 0$. This shows that on this side we approach the positive $+\sqrt{1-x^2}$.
	To see that the other side converges to the negative branch, consider that the residues of $f'/f$ at its poles are $\pi i$, hence sign switches when going around $\pm 1$ (similar to the work done in problem 4.)

	<br>
	Another strategy is to use the substitution $u = z^{-1}$, which transforms integral to be over $|z| = 1/2$ with a single pole inside, allowing us to use the residue theorem. 
	Note that finding the residues can be difficult due to choice of branches. 

	<br>
	For $J$ consider the contour that is a large semicircle of radius $R > 0$ with smaller semicircles of radius $r$ cut out at the points $z = \pm 1$. <br>
	<img src="/assets/complex-ex-4/circle_contour.png" class="center" alt="Circular contour avoiding poles on real axis"><br>
	Over this contour we will integrate $$ f(z) = \frac{z e^{\pi i z}}{1-z^2}.$$
	First, note that on the largest semicircle we have 
	$$ \begin{align*} \left| \int_{\gamma_R} f(x)\,dx \right| &\leq 2\int_0^{\pi/2} \frac{R^2}{R^2-1} e^{-\pi R\sin \theta}\,d\theta \\&\leq 2\int_0^{\pi/2} \frac{R^2}{R^2-1} e^{-2 R\theta}\,d\theta \\&=  \frac{R^2}{R^2 - 1} \left[ \frac{1}{2R} - \frac{1}{2R}e^{-\pi R} \right] \end{align*}$$
	which converges to zero as $R \to \infty$. 
	Now, taking the limit as $r\to 0$ of the small circles around the poles at $z = \pm 1$ we see that each circular arc's integral approaches $-\pi i\text{res}_{z = \pm 1}(f)$ (this is because we can write $f(z) = R/(z-p) + g(z)$ where $R$ is the residue at $z = p$ and $g(z)$ is holomorphic near $z = p$. Integrating on the half arc will arrive at $-\pi i R.$ See Ahlfors 4.5.3.) 
	Quick calculations show that
	$$ \text{res}_{z=1}(f) = \text{res}_{z= -1}(f) = \frac{1}{2} $$
	hence by applying Cauchy's theorem and letting $R\to \infty, r\to 0$ we find 
	$$\int_\mathbb{R} f(z)\,dz = \pi i $$
	and finally, equating imaginary parts and dividing by 2 (due to evenness of the integrad) we arrive at
	$$ J = \frac{\pi}{2} $$
</details>


Problem 12 (Prelim January 2014)
------
Suppose $f$ is an entire function with the property that $f(z)$ is real if and only if $z$ is real. Show that $f'(z) \ne 0$ for all real $z$. 
<details>
	<summary>Hint</summary>
	If $f'(w) = 0$ consider applying the argument principle to $f(w) - w$. 
</details>
<details>
	<summary>Solution</summary>
	Following the hint, we  can suppose that $f(w)$ is a function with a double root at the origin. The argument principle says if $\gamma_r(\theta) = re^{i\theta}$ is any positively oriented circle of radius $r > 0$ we have
	$$ 4\pi i = \int_{\gamma_r} \frac{f'(z)}{f(z)}\,dz = 2\pi i n(f\circ \gamma_r,0).$$
	Note however, that the curve $f\circ \gamma_r$ can only intersect the real axis twice - at $\theta = 0,\pi$. 
	For $\theta \in (0,\pi)$ we must have that $f\circ \theta$ is entirely in the upper or lower half plane, and upon hitting $\mathbb{R}$ again at $\theta = \pi$ the argument will have either changed to $\pm \pi$ (in the case that $f(r),f(-r)$ have different signs) or $0$ (if the signs are identical.) 
	Repeating this argument between $(\pi, 2\pi)$ we arrive at $n(f\circ \gamma_r,0) = \pm 1$ or $0$, which contradicts the existence of a double root at the origin. 
</details>
