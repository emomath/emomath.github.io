---
layout: post
title: First chunk-of Number Theory Exercises
date: 2025-07-05 16:57:03 +0200
categories: jekyll update
---

## Exercise 4

> Show that for all $a$ and $b \in \mathbb{Z}$ and for all $n \in \mathbb{N}$: $(a-b) \mid (a^n - b^n)$ 

### Proof

$$
(a-b)(\sum_{k=0}^na^{n-k}b^k) = \sum_{k=0}^na^{n+1-k}b^k -\sum_{k=0}^na^{n-k}b^{k+1} = a^{n+1} + \sum_{k=1}^na^{n+1-k}b^k -\sum_{k=0}^{n-1}a^{n-k}b^{k+1} -b^{n+1} = 
$$

$$ = a^{n+1} + \sum_{k=0}^{n-1}a^{n-k}b^{k+1} -\sum_{k=0}^{n-1}a^{n-k}b^{k+1} -b^{n+1} = a^{n+1}-b^{n+1}
$$
$\square$ 

## Exercise 5

> Show that for all $a$ and $b \in \mathbb{Z}$ and for all $n,m \in \mathbb{N}: m|n \implies (a^m-b^m) \mid (a^n - b^n)$ 

### Proof
Let $m|n$ for $n,m \in \mathbb{N}$. Then there exists $d \in \mathbb{N}$ such that $md = n$. We write $(a^n - b^n) = ((a^m)^d - (b^m)^d)$. Now if we substitut $x = a^m, y= b^m \in \mathbb{N}$ by the first exercise we get that $(x-y) \mid (x^d - y^d) \implies (a^m-b^m) \mid (a^n - b^n)$. $\square$ 

## Exercise 6

>Show when $2 \nmid n$ for some $n \in \mathbb{N}$ then $8 \mid (n^2 +23)$ 

### Proof
Let $n \equiv d\ (\text{mod}\ 8)$ with $2 \nmid d$ and $d \neq 0$. Looking at the multiplication table of $Z/8Z$ we see that all $d^2 = 1\ (\text{mod}\ 8)$. From this fact we obtain: 

$$
n^2 + 23 \equiv d^2 + 7 \equiv 0\ (\text{mod}\ 8)
$$
$\square$ 

### Exercise 7

> Show when $3 \nmid n$ for $n \in \mathbb{N}$ then $3 \mid n^2 + 23$

### Proof 
Let $n \equiv d\ (\text{mod}\ 3)$ with $d \neq 0$. Looking at the multiplication table of $Z/3Z$ we see that all $d^2 = 1\ (\text{mod}\ 3)$. From this fact we obtain: 

$$
n^2 + 23 = d^2 + 2 = 1 + 2 = 0\ (\text{mod}\ 3)
$$
$\square$ 




