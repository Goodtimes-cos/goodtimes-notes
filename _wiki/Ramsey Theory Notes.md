---
published: true
subtitle:
date: 2024-06-25
tags: maths
---

# Ramsey Theory Notes
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
 - Prove that for every $s,t \in \mathbb{N}, R(s,t) \leq (s+t-2) C (s-1)$. In particular, $R(t,t) \leq (2t-2) C (t-1) < 2^{2t-2}$. (Hints: What case can we assume for $s, t$? What do we assume by induction?
   How do you prove the first part of the corollary, using the above and the
   binomial identity? How do we prove the latter quantity?)
- Prove that for all $t \in \mathbb{N}$, $R(t) \leq 2^{2t-1}$ holds. (Hints: Let $n=$? How do we guarantee a monochromatic copy of $K_t$? How many edges are adjacent to an arbitrary vertex? How many times do we repeat this process? What two criterion does the resulting sequence satisfy?)
- What is the definition of $R_k(s_1, \dots, s_k)$?
- How do we prove the above exists?