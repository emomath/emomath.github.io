---
layout: post
title:  "A personal Proof of a special Version of the Spectral Theorem"
date:   2025-07-05 16:57:03 +0200
categories: jekyll update
---

## Theorem
> Let $A$ be as self-adjoint endomorphism over the finitely dimensional unitary vector space $V$. Then $A$ is orthogonally diagonalizable.

## Sketch of proof: 
Our central argument will be that for any eigenvalue of $A$ the algebraic multiplicity will be equal to the geometric multiplicity of the eigenvalue. From this it follows that $A$ has a basis of eigenvalues, since the degree of the characteristic polynomial of $A$ is equal to the dimension of V. We proceed in the argument as follows:
1. All eigenvalues of $A$ are real. 
2. It suffices to show that the algebraic multiplicity of $0$ over $A - \lambda I$ is equal to the geometric multiplicity of the eigen space of $0$ over $A - \lambda I$. This implies the same for $\lambda$ over $A$.
3. $A - \lambda I$ is self-adjoint. 
4. The algebraic multiplicity of $0$ over $A - \lambda I$ is equal to the geometric multiplicity of the eigen space of $0$ over $A - \lambda I$.
5. Eigenvectors are pairwise orthogonal

## Proof:
Let $n =$ dimension of V.

1: Let $\lambda$ be an eigenvalue of $A$. 

$$
\lambda \langle x,x \rangle = \langle Ax
,x \rangle = \langle x,Ax \rangle = \overline \lambda \langle x,x \rangle 
$$

From this it follows that $\lambda$ is real. 

2: We want to show that the algebraic/geometric multiplicity of $0$ over $A - \lambda I$ is equal to the algebraic/geometric multiplicity of $\lambda$ over $A$ respectively. 

Let $\prod_{i=1}^{n}(\mu_i-y)^{\upsilon(i)}$ be the linear factor decomposition of the characteristic polynomial $\chi_A(y) = \det(A-yI)$ of $A$. $\upsilon(i)$ denots the algebraic multiplicity of $\mu_i$ and let $a$ denote the algebraic multiplicity of $\lambda$ over $A$.

$$
\chi_{A-yI}(y) =  \det(A-\lambda I - yI) = \det(A-(\lambda+y)I) = \chi_A(\lambda + y) = \prod_{i=1}^{n}(\mu_i - \lambda - y)^{\upsilon(i)}
$$

Since for one $i \in \{1,…,n\}$ $\mu_i = \lambda$ we see that the algebraic multiplicity of $\lambda$ over $A$ is the same as the algebraic multiplicity of $0$ over $A - \lambda I$. 
Intuitively this makes sense, since essentially what we are doing is moving the polynomial $\chi_A$ along the x-axis. This should preserve the general structure of roots of the polynomial.
For the geometric multiplicity simply observe that $A -\lambda I = 0 \iff Av = \lambda v$. 

3: We want to show that $A - \lambda I$ is self-adjoint. Let $x,y \in V$. 

$$
\langle (A-\lambda I)x,y \rangle = \langle Ax - \lambda x,y \rangle = \langle Ax,y \rangle - \langle \lambda x,y \rangle = \langle x,Ay \rangle - \langle x,\lambda y \rangle= \langle x,(A-\lambda I)y \rangle 
$$

> Remark: The third equation sign is only true because $\lambda$ is real, which we proved in the first step. 

4: We want to show that the algebraic multiplicity of $0$ over $A - \lambda I$ is the same as the geometric multiplicity of $0$ over $A - \lambda I$. We proceed by contradiction: 

> Remark: We only have to check the case that the algebraic multiplicity of $\lambda$ is bigger than the geometric multiplicity. This is the case because we can change the canonical basis to a basis of all eigenvectors with the respectiv eigenvalue ensuring we get that the factor $(x - \lambda)^{\text{dim(Eig}(A,\lambda))}$ divides the characteristic polynomial. 

Assume that the algebraic multiplicity of $0$ is bigger than the geometric multiplicity. Since the geometric multilicity is smaller or equal to the algebraic multiplicity for all eigenvalues by the Caley-Hamilton Theorem it follows that the generalized eigenspace of $(A -\lambda I)$ has to be bigger than the eigenspace.
From this it follows that we can pick $w \in V$ such that $w \not \in  \text{Eig}(0, A - \lambda I)$ and $Aw = v$ with $v \not = 0$. This is true since if $(A-\lambda I)^{r}(x) = 0$ then we pick  $(A-\lambda I)^{r-2}(x)$ as $w$. 

Inspect the following: 

$$
\langle (A- \lambda I)^2 w,w \rangle = 0 \iff \langle (A- \lambda I) w, (A - \lambda I)w \rangle = \langle v, v \rangle = 0 \implies v = 0 
$$

This is a contradiction to  $v \not = 0$. This means our assumption that the generalised eigen space was bigger than the eigen space of $(A- \lambda I)$ has to be wrong. So the algebraic multiplicity has to equal the geometric multiplicity. By the second step we know that this also holds true for $\lambda$ thus proving that $A$ is diagonalizable.

> Remark: The argument only works, because $(A - \lambda I)$ is a self-adjoint endomorphism. We proved this in the third step. 

5: It remains to be shown that the eigen vectors of $A$ form an orthogonal basis. Let $w,v \in V$ be two eigenvectors with $\lambda \not = \mu$ as their respective eigenvectors. 

$$
\lambda \langle w,v \rangle = \langle Aw
,v \rangle = \langle w,Av \rangle = \mu \langle w,v \rangle
$$

This implies $\langle w,v \rangle = 0$. 
Now consider a basis for the eigen space of $\lambda$. We can make this basis orthogonal by doing the Gram-Schmidt Algorithm. Since the eigen space is a vector space the new orthogonal basis stays in the eigen space thus proving the claim. $\square$   

