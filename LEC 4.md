# QR Factorization

## Orthogonal Set of Vectors

### Definition

- We said a set of vectors $u_1, u_2, \dots, u_k \in R^n$ is
- 1. Orthogonal if $u_i \perp u_j, i\ne j$
	2. Normalized if $||u_i|| = 1$
	3. Orthonormal if both
- Notice that orthogonal is for a set of vectors not individually, for $U = [u_1, u_2, \dots, u_k]$ is orthonormal, $U^TU = I_k$
- Obviously, they are independent, but if $k < n \Rightarrow UU^T \ne I_n$

### Geometric properties

- **Isometric**: Suppose  $U = [u_1, u_2, \dots, u_k]$ is orthonormal, if $w= Uz \Rightarrow ||w|| = ||z||$, easy to prove $||w|| = w^Tw = z^TU^TUz= ||z||$, this is called isometric, which means mapping will preserve the distances
- Also, it will preserve the **inner product and angles**, easy to prove $<w, v> = <Uw, Uv> = w^TU^TUv = w^Tv$
- Thus, multiplication by U keeps **distance, inner product and angles**

### Orthogonal Basis

- Suppose $U= [u_1, u_2, \dots, u_n]$ is an orthonormal basis for $R^n$, then it satisfies $UU^T$

## Gram-Schmidt Procedure

## Orthogonal Decomposition Induced by a Matrix

