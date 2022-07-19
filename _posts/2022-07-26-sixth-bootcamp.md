---
title: 'Complex Bootcamp Exercises: Normal Families'
date: 2022-07-26
permalink: /posts/2022/07/bootcamp-2022-ex-6/
tags:
  - bootcamp
  - complex analysis
---

This set of problems focuses on normal familities (aka precompact sets) of functions, Picard's theorem, Jensen's formula, and other topics.

Resources
------
Ahlfors sections 5.5 and 8.3

Problems
======

Problem 1
------
	Let $f$ be an entire function satisfying $f(1-z) = 1-f(z)$. Show that $f(\mathbb{C}) = \mathbb{C}$. 
<details>
	<summary>Hint</summary>
	Suppose not and apply Picard then $f(\mathbb{C}) = \mathbb{C} \setminus \\{z_0\\}$ and find a contradiction. 
</details>

Problem 6 (Prelim August 2020)
------
Suppose that $f$ is analytic on $\mathbb{D}$ and satisifies $|f(z)| \leq M$ for all $z\in \mathbb{D}$. Assume further that $f$ vanishes at the points $\\{z_j\\}_{j=1}^N$ where $1 \leq N \leq \infty$.)
If $N = \infty$ and $f \ne 0$ then show that $$ \sum_{j=1}^\infty (1-|z_j|) < \infty. $$
<details>
	<summary>Hint</summary>
	Jensen's formula. 
</details>
