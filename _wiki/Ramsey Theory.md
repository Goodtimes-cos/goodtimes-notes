---
published: true
subtitle:
date: 2024-06-25
tags: maths
---

# Ramsey Theory
- What is the pigeonhole principle with regards to ramsey theory?
- How do you prove the above?
- What is the definition of a Ramsey number?
- Prove that $R(3,3) = 6$.
- Prove the following:
	- $R(1, t) = 1$,
	- $R(s,t) = t$,
	- $\exists R(s,t) \rightarrow R(s,t) = R(t,s)$. 
- Prove that $R(s,t)$ exists, and that for $s,t \geq 2, R(s,t) \leq R(s-1,t) + R(s,t-1)$. (Hints: What case can we assume? What values do $p$
 and $q$ take? How many edges do we assume are incident with $x$? What
 will this choice yield?)
 - Prove that for every $s,t \in \mathbb{N}, R(s,t) \leq {s+t-2 \choose s-1}$. In particular, $R(t,t) \leq {2t-2 \choose t-1} < 2^{2t-2}$. (Hints: What case can we assume for $s, t$? What do we assume by induction?
   How do you prove the first part of the corollary, using the above and the
   binomial identity? How do we prove the latter quantity?)
- Prove that for all $t \in \mathbb{N}$, $R(t) \leq 2^{2t-1}$ holds. (Hints: Let $n=$? How do we guarantee a monochromatic copy of $K_t$? How many edges are adjacent to an arbitrary vertex? How many times do we repeat this process? What two criterion does the resulting sequence satisfy?)
- What is the definition of $R_k(s_1, \dots, s_k)$?
- How do we prove the above exists? (Hints: Proceed by induction on $k$. Assume holds for $k-1$. What are variables $m and n$? Why does $n$ hold? Consider colourings $c and \tilde{c}$. Consider what structures
  exists based on $\tilde{c}$, what are the consequences of these?)
  - How do we prove that $R(3,4) = 9$? (Hint: Consider the three cases: at least 4 red edges, at least 6 blue edges, exactly 3 red edges and 5 blue edges. From this, what may we conclude? Next, how can we prove that a r/b-edge-colouring of $K_8$ has no red $K_3$ nor blue $K_4$?)
  - How can we use the random colouring proof to show that, for $t,n \in \mathbb{N}$, if ${n \choose t}2^{1 - {t \choose 2}} < 1$, then $R(t) > n$? (Hint: How may we colour the edges independently and of equal probability? Must all coin flips be mutually independent? How many sets of $t$ vertices exist? How many will be red? How many blue? What is the value of $\mathbb{E}(X)$? Why is it important that $X$ must be a non-negative integer?
  - For every $t \geq 4$, $R(t) > \floor{2^{\frac{t}{2}}}$ holds. (Hint: What value should $n$ take? By theorem 1.13, what must we prove? From here we may simply derive.)
  - What is the definition of $X^{(r)}$?
  - What is the definition of $R^{(r)}(s,t)$?
  - Prove that for any $s,t \geq r \geq 1$, $R^{(r)}(s,t)$ is finite and satisfies $R^{(r)}(s,t) \leq R^{(r-1)}(R^{(r)})(s-1, t), R^{(r)}(s, t-1)) + 1$.
  - Prove that for $m \geq 4$, there exists $n \in \mathbb{N}$ such that any set of $n$ points in $\mathbb{R}^2$, no three of which on a line, contains $m$ points that form a convex $m$-gon. (Hint: Among five points, none on the same line, there are always four points in a convex position. If any four of m points are in a convex position, then they are all in a convex position.)
  - How do you prove Schur's theorem. That is, prove that for all $r \in \mathbb{N}$, there exists $n = n(r)$ such that in every r-colouring of $[n]$, there exist integers $x,y,z \in [n]$ all coloured with the same colour such that $x+y=z$. (Hint: Consider $R_r(3,\dots,3))$, and let $c$ of $[n]$. How can we define an suitable r-edge-colouring $c'$ of $K_n$?)
  - Prove that for all $s, t \in \mathbb{N}$, any sequence $a_1, \dots, a_n$ of $n > st$ distinct real numbers contains an increasing subsequence of length $s+1$ or decreasing subsequence of length $t+1$. (Hint: Consider either the piles proof or function proof. Both need close analysing)
  - What is the Van der Waerden number of $r, m$, denoted $W(r, m)$?
  - How can we prove that for all $r, m \in \mathbb{N}, W(r, m)$ exists?
  - For arithmetic progressions $A_1, \dots, A_k$, what does it mean for them to be focused?
  - Prove that for any $r, m, k \in \mathbb{N}$ with $k \in [r]$, there exists an integer $n = n(r, m, k)$ such that any r-colouring of $[n]$ has either a monochromatic arithmetic progression of length $m$, or a set of $k$ focused arithmetic progressions $A_1, \dots, A_k$ of length $m-1$, each of which is monochromatic in a different colour, and whose focus f is at most $n$ (or both).
  - The last three are interconnected :3