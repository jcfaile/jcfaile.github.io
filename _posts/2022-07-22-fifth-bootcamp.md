---
title: 'Complex Bootcamp Exercises: Products and Series'
date: 2022-07-22
permalink: /posts/2022/07/bootcamp-2022-ex-5/
tags:
  - bootcamp
  - complex analysis
---

This set of problems focuses on series and product representations of holomorphic and meromorphic functions. 

Resources
------
Ahlfors chapter 5.1 - 5.2.3 and 5.3.2

Problems
======

Problem 1 (Prelim August 2015)
------
	Let $\mathbb{D} = \\{z: |z| = 1\\}$ and $\mu$ Lebesgue measure on this set. Let $H\subset L^2(\mathbb{D}, \mu)$ be the subset of holomorphic functions. 
	Show that $H$ is closed with respect to the $L^2$ norm. 
<details>
	<summary>Hint 1</summary>
	Show that for every compact $K\subset \mathbb{D}$ there exists $C_K > 0$ such that $\norm{f|_K}_{\infty} \leq C_K \norm{f|_K}_{2}$. 
</details>
<details>
	<summary>Hint 2</summary>
	If we fix a ball $B$ of suitably small radius $r$ at any point $z_0 \in K$ then integrate over it we find $$f(z_0) = \frac{1}{\mu(B)} \int_B f(z)\,dz$$ by the mean value property. 
	Additionally, note that on bounded domains there exists $C>0$ (depending on the domain and $1 \leq p < q$) such that $\norm{f}_p \leq C\norm{f}_q$. 
</details>

Problem 1 (Prelim August 2015)
-----
Let $\mu$ be Lebesgue measure on $\mathbb{D}$. Let $H \subset L^2(\mathbb{D},\mu)$ be the subset of holomorphic functions. 
Show that $H$ is a closed subset.
<details>
	<summary>Hint</summary>
	Show that for every compact subset $K \subset \mathbb{D}$ there exists a constant $C_K > 0$ depending only on $K$ such that $$ \sup_{z\in K} |f(z)| \leq C_k \lVert f|_K \rVert_{L^2}.$$
	We can relate the value of $f$ at a point to its integral via the mean value property. 
</details>
