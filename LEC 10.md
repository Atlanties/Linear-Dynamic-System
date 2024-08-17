# Solutions via Laplace transform and matrix exponential

## Laplace transform

### Definition

- Laplace Transform is introduced to turn a differentiate problem into a linear problem
- Laplace Transform: $\text{Suppose }z: R_{+} \rightarrow R^{p\times q}$
$$
Z = \mathcal{L}(z)\text{, where } Z: D \subseteq \bold{C} \rightarrow \bold{C^{p\times q}}\text{, is defined by }\\
Z(s) = \int_{0}^{\infin} e^{-st} z(t) dt
$$

- The integral of Matrix is done term by term
- D is the convergence domain



### Derivative property

- $\mathcal{L}(\overset{.}{z})(s) = sZ(s) - z(0)$
- PF.

$$
\begin{aligned}
\mathcal{L}(\overset{.}{z})(s) &= \int_0^{\infin} e^{-st}\overset{.}z(t)dt\\
&=  e^{-st}z(t)\bigg|_{0}^{\infin} + s\int_0^{\infin} e^{-st}z(t)dt \\
&= s\mathcal{L}({z})(s) - z(0)
\end{aligned}
$$



## Solving $\overset{.}{x}=Ax$ via Laplace transform and State Transform Matrix

- $x(t) = \mathcal{L}^{-1}(SI - A)^{-1}x(0)$
- $(SI-A)^{-1}$ is called **resolvent** of A, it is excepted for those, i.e., s makes $det(SI-A) = 0$
- $\Phi(t) = \mathcal{L}^{-1}(SI - A)^{-1}$ is called ***state-transition matrix***; $x(t)=\Phi(t)x(0)$



## Characteristic polynomial and Eigenvalues

- We can describe $det(sI-A) = \chi(s)$ as the characteristic polynomial and the roots of it are eigenvalues, the numbers of eigenvalues are $n=Rank(sI-A)$
- If coefficients of $\chi(s)$ are real, eigenvalues can only be **real** or **conjugate pairs**
- From Cramer's rule, we have the i, j entry of resolvent: $(-1)^{i+j}{det\Delta_{ij}\over det(sI-A)^{-1}}$



## Matrix Exponential

- Matrix Exponential **is not** doing exponential term by term, it is just an approximation of Tayler polynomials for exponential functions
- Matrix Exponential:

$$
(I-C)^{-1} = I + C + C^2 + \dots \text{(if series converges)} \\
(SI - A)^{-1} = (1/s)(I-A/s)^{-1} = {I\over{s}} + {A\over{s^2}} + {A^2\over{s^3}}+\dots 
\text{(valid only if s is large enough)} \\
\Phi(t) = I + tA + {(tA)^2\over2} + \dots \\
\text{Define matrix exponential as follwings:} \\
e^M = I + M + {M^2\over2} + \dots\\
\text{so, state-transition matrix is:} \\
\Phi(t) = e^{tA}
$$

- Remember: Matrix Exponential is only similar to exponential but not the same, it only represents a polynomial,  so obviously, matrix multiplication is not the same as scalar multiplication

 

## Qualitative behavior and stability

### Qualitative Behavior of x(t)

- Suppose ${\overset{.}x}=Ax\Rightarrow x(t)=e^{At}x(0); X(s)=((sI-A)^{-1})x(0)$, regarding $X_i(s)$ as a vector with n entries, then the $X_i(s) = {a_i(s)\over \chi(s)}$
- From Cramer's rule we can know that, $a_i(s)$ has degrees less than $\chi(s)$
- Obviously, $\chi(s)$ has eigenvalues as the poles, so by Laplace Transform we have $x_i(t)=\sum_{j=1}^n\beta_{ij}e^{\lambda_jt}$, here $\lambda_j$ are the eigenvalues of $\chi(s)=det(sI-A)$
- For those have complex eigenvalues $\sigma+j\omega$, we still have the terms like $e^\sigma cos(\omega t+ \phi)$
- **Conclusion**: $\mathcal{R}\lambda_j$ the real part gives the **growth or decay rate**, $\mathcal{C}\lambda_j$ the complex part gives the **frequency or oscillatory** term
- For those not distinct eigenvalues, we have: $x_i(t)=\sum_{j=1}^np_{ij}(t)e^{\lambda_jt}$, from Laplace transform we know that for those eigenvalues repeats n times, we got polynomials at most for degree n

### Stability

- Conclusion: iff we got all $\lambda$ eigenvalues **negative**
