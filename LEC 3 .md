# Linear Algebra Review

## Vector Space

- DEF: Vector Space is a linear space which satisfies sum/scalar multiplication closure and contains 0 element, mathematical description like below:

$$
\forall \vec{u}, \vec{v} \in \mathcal{V}, a \in R,\text{ satisfies:} \\
\vec{u} + \vec{v} \in \mathcal{V}, a\vec{u} \in \mathcal{V}, \vec{0} \in \mathcal{V}
$$

- **Span**: span means the set contains all linear combination of a set of vectors,

$$
span(v_1, v_2, \dots,v_n) = \{\alpha_1v_1 + \cdots + \alpha_kv_k| \alpha_i \in \mathbb{R}\},\{v_1, v_2, \dots, v_k \in R^n\}
$$

- **Subspace**: a subset of a vector space, and itself is a vector space

- **Vector space of functions**: functions can also have vector space

$$
\mathcal{V} = \{x: R^m \rightarrow R^n\} \\
\text{where } (x_1 + x_2)(t) = x_1(t) + x_2(t)
$$

- **Independence of vectors**:

$$
\{v_1, v_2, \dots, v_n\} \text{ is independent iff:} \\
\alpha_1v_1 + \alpha_2v_2 + \dots + \alpha_nv_n = 0 \Rightarrow \alpha_1 = \alpha_2 = \dots = \alpha_n = 0
$$

​		which means no vector can be expressed as linear combination of other vectors

- **Basis and dimension**: Every vector in vector space $\mathcal{V}$ can be expressed as linear combinations of basis and basis is independent, the numbers of vectors in basis is *dimension*

$$
\mathcal{V} = span(v_1, v_2, \dots, v_n)\\
dim(\mathcal{V}) = n
$$

## Nullspace and Range

### Nullspace

- **Nullspace**: Null space is a concept for matrix, the *nullspace* of matrix $A\in R^{m\times n}$ is $\mathcal{N}(A) = \{x \in R^n | Ax = 0\}$
- **Prop 1.** Nullspace contains all vectors that mapped to zero by $y=Ax$, which also means that all vectors in nullspace are *orthogonal* to all rows of A
- **Prop 2.** Mapped result won't change when plus a vector in nullspace, $z \in \mathcal{N}(A), y = Ax = A(x+z)$
- **Prop 3.** Nullspace gives ambiguity for our design, which is good in design problems, but bad in observation or measurement problems



### Zero Nullspace

- **Zero Nullspace**: Zero Nullspace means the no vectors in null space, $\mathcal{N}(A) =\{\vec{0}\}$
- **Prop 1.** All column vectors of A are independent, as only all coefficients equals to zero will get the 0 result
- **Prop 2.** A has a left inverse, which means $B\in R^{n\times m},BA = I, det(A^TA) \ne 0$, $Rank(A) = n$
- **Prop 3.** Mapping from x to y is unique



 ### Brief for nullspace

- Nullspace characterizes the freedom of input choice for given result
- Nullspace characterizes the ambiguity in x from measurement $y=Ax$



### Range

- **Range:** $\mathcal{R}(A) = \{Ax|x\in R^n\} \sube R^m$
- **Prop 1.** Range describes the set of vectors that A can map, the span of columns of A and the set of vectors y for which $y=Ax$ has a solution



### Full Range

- **Onto**: A is called onto if $\mathcal{R}(A) = R^m$
- **Prop 1.** Any y can be solved for $y=Ax$, and columns of A spans $R^m \Rightarrow Rank(A) = m$ which means A is row independent
- **Prop 2.** $\mathcal{N}(A^T)= {\vec{0}}, det(A^TA) \ne 0$



### Brief for Range

- **Measurement**: which results are **achievable**
- **Output**: Characterize the possible result



### Inverse

- Matrix $A \in R^{n \times n}$ is invertible or nonsingular if $det(A) \ne 0$
- $\mathcal{N}(A) = 0$
- $R(A) = R^n$
- **Interpretation**: reverse mapping
- **Dual basis**： suppose $a=(a_1, a_2,\dots a_n)$ and $b^T=(b_1, b_2,\dots,b_n)$, $ab=I$, $y=ax$ we have:

$$
y = \sum_{i=1}^n(b_iy)a_i
$$

​		we call a and b are **Dual basis**.



## Rank 

- **Rank**: Rank of a matrix $A^{m\times n}$ defined as  $rank(A)=dim\mathcal{R}(A)$
- **Property**:

$$
rank(A) = rank(A^T)\\
rank(A) \leq min(m,n)\\
rank(A) + dim\mathcal{N}(A) = n \\
$$

- **Interpretation**: the input will either be mapped to range or crushed to zero, n is the freedom of degree in input of x, $dim\mathcal{N}(A)$ is the freedom of degrees loss in mapping, $rank(A)$ is the freedom of degrees in output
- **Rank of product**: $A=BC, rank(A)<min\{rank(B), rank(C)\}$, so if $rank(A)=r$, we can reconstruct A by at most r vectors, $A=BC, B \in R^{m\times r}, C \in R^{r\times n}$
- **Applications Fast matrix-vector multiplication:** By dividing $A=BC \Rightarrow Ax = B(Cx)$, the former multiplications have $mn$ operations, later one have $(m+n)r$ operations, if the $r \ll min\{m, n\}$ we can get considerable optimization
- **Full rank:** if $A \in R^{m\times n}, rank(A)= min\{m,n\}$, we say that $A$ is full rank



## Coordinates

- **Definition**: coordinates is a vector which represent how to get it by linear combination of basis, eg.

$$
\text{Standard basis for }R^n \text{ is }(e_1, e_2, \dots, e_n), x\in R^n\\
x = x_1e_1 + x_2e_2 + \dots + x_ne_n, \{x_1, x_2,\dots, x_n\} \text{ are coordinates of x for e}
$$

- **Change Coordinates**: if we got another basis $T=(t_1, t_2, \dots, t_n)= Te$ of $R^n$, we have 

$$
x = Tx^{'} = x_1^{'}t_1 + x_2^{'}t_2 + \dots + x_n^{'}t_n,x^{'}=T^{-1}x \\
y = Ax \Rightarrow y^{'}= Ty = (T^{-1}AT)x^{'}
$$

- **Similarity Transformation**: $A\rightarrow T^{-1}AT$ is called similarity transformation, which express linear transformation of $y=Ax$ in coordinates $t_1, t_2, \dots, t_n$

## Norm

- **(Euclidean) Norm**: For $x\in R^n$ , we define Euclidean norm(p-norm, p=2) as 

$$
||x|| = \sqrt{x_1^2 + x_1^2 + \cdots + x_n^2}= \sqrt{x^Tx}
$$

- **Properties of Norm**: these work for every p-Norm

$$
||\alpha x|| = |\alpha| ||x|| \text{ (homogeneity)}\\
||x+y|| \le ||x|| + ||y|| \text{ (triangle inequality)} \\
||x|| > 0 \text{ (nonnegativity)}\\
||x|| = 0 \Leftrightarrow x = \vec{0} \text{ (definiteness)} \\
$$

- **Root Mean Square(RMS)**: defines mean distance to original point from all dimensions

$$
\bold{rms}(x) = ({1\over n}\sum_{i=1}^n x_i^2)^{1/2} = {||x|| \over n}
$$



- **(Euclidean) Distance**: defines distances between vectors $\bold{dist}(x, y)= ||x-y||$



## Inner Product

- **Definition**: sum of multiplications of each entries of two vectors(algebra), multiplications of two length of two vectors and the cosine of angles $cos\theta$ (geometry)

$$
<x, y> = x_1y_1 + \dots + x_ny_n = x^Ty
$$

- **Properties**:

$$
<\alpha x, y> = <x, \alpha y> = \alpha <x, y> \\
<x+y, z> = <x, z> + <y, z> \\
<x, y> = <y, x> \\
<x, x> \ge 0 \\
<x, x> = 0 \Leftrightarrow x = \vec{}0
$$

​		obvious, $f(y) = <x, y>$ is a linear function



## Cauchy-Schwartz Inequality 

- **Definition**: $x^Ty \le ||x||||y||$
- From geometry definition, we get $<x, y> = ||x||||y||cos\theta$, obviously we get the result, actually C-S inequality works for many areas, like calculous and statistics
- **Halfspace**: $\{x|x^Ty \le 0\}$ defines a *halfspace* with outward norm vector y including boundary

