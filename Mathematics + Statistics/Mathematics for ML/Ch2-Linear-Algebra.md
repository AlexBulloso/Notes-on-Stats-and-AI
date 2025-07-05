# Ch2. Linear Algebra

#### 2.0 Intro

- Linear algebra is the study of vectors and rules to manipulate vectors. These are usually denoted with $\vec{x}$ and $\vec{y}$. In general, vectors can be added together and multipled by scalars to form another vector.

The following are examples of vectors:
- Geometric vectors are vectors which can be drawn in at least two dimensions. 
    - $\vec{x} + \vec{y} = \vec{z}$
    - $\lambda \vec{x}$ is a vector, where $\lambda \in \mathbb{R}$
- Polynomials are also vectors. They can be added together and multipled by a scalar to form another vector.
- Audio signals are vectors.
- Elements of $\mathbb{R}^{n}$ (tuples of $n$ real numbers) are vectors:
$$\bf{a} = \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix} \tag{2.1}$$ 
    - This object still satisfies the previous rules:
        - $\bf{a} + \bf{b} = \bf{c}, \bf{c} \in \mathbb{R}^n$
        - $\lambda\bf{a} \in \mathbb{R}^n$

- Book focuses on finite dimensional vector spaces with 1:1 correspondence between vectors and $\mathbb{R}^n$
- Vector spaces refer to the set of vectors from a small set and adding or scaling them.

    
    

#### 2.1 Systems of linear equations

##### Example 2.1
- There are n types of products, $N_1, N_2, \ldots, N_n$. The number of each product we want to make is $x_1, x_2, \ldots, x_n$. Let $N_j$ be the one of the products, where $j=1,2,\ldots,n.$
- There are $m$ types of resources, $R_1, R_2, \ldots, R_m$. Let $R_i$ represent one of the resources, where $i=1,2,\ldots,m$. There is a limit to each of these resources, denoted by $b_i$. 
- To make a unit of $N_j$, $a_{ij}$ (a set constant) units of $R_i$ are needed
- If we want to produce $x_i$ units of the corresponding product ($N_i$), you would need $x_i \times a_{ij} \times R_i$. Note that $b_i$ is the number of $R_i$ available.
- To optimise $(x_1,\ldots,x_n)\in\mathbb{R}^n$, the following must be satisified:
$$
a_{11}x_1+\dots+a_{1n}x_n=b_1 \\
\vdots \\
a_{m1}x_1+\dots+a_{mn}x_n=b_m
$$

##### Remark
- For a system of linear equations with two variables, the possibilities are interesection (point), line (if same line) or none (if parallel).
- For 3D space, each equation describes a plane. To satisfy all linear equations at the same time, you can obtain a plane, line, point, or empty space.
- Matrix notation:
$$
x_1\begin{bmatrix}a_{11} \\ \vdots \\ a_{m1}\end{bmatrix} + \dots + x_n \begin{bmatrix}a_{1n} \\ \vdots \\ a_{mn}\end{bmatrix} = \begin{bmatrix}b_{1} \\ \vdots \\ b_{m}\end{bmatrix} \\
\Longleftrightarrow\begin{bmatrix}a_{11} & \dots & a_{1n}\\ \vdots & & \vdots \\ a_{m1} & \dots & a_{mn} \end{bmatrix} \begin{bmatrix}x_{1} \\ \vdots \\ x_{n}\end{bmatrix} = \begin{bmatrix}b_{1} \\ \vdots \\ b_{m}\end{bmatrix}$$

#### 2.2 Matrices
- Matrix addition ($\bf{A}\in\mathbb{R}^{m \times n}, \bf{B}\in\mathbb{R}^{m \times n}, \bf{A}+\bf{B}$) involves addition of the elements in each position.
- For matrix multiplication, we have $\bf{A}\in\mathbb{R}^{m \times n}, \bf{B}\in\mathbb{R}^{n \times k}$. Note that neighbouring dimensions must match. The product of the matrices is: $\bf{C} = \bf{AB}$, where $\bf{C} \in \mathbb{R}^{m \times k}$. The element $c_{ij}$ in the product $\bf{C}$ is equal to:
$$c_{ij} = \sum_{l=1}^{n}a_{il}b_{lj} \\ i = 1, \ldots, m. \quad j = 1, \ldots, k.$$
    - Element wise multiplication is not the same as matrix multiplication (this is instead called the Hadamard product). 
- Identity matrix: $n \times n$-matrix containing 1 on the diagonal and 0 everywhere else.
##### Matrix properties
- The following assumes consistent dimensions:
- Associativity: $\forall \bf{A,B,C}: \quad (\bf{AB})\bf{C} = \bf{A}(\bf{BC})$
- Distributivity:$\forall \bf{A,B,C,D}:$
$$(\bf{A}+\bf{B})\bf{C} = \bf{AC}+\bf{BC} \qquad
\bf{A}(\bf{C}+\bf{D}) = \bf{AC}+\bf{AD}$$
- Multiplication with identity matrix will yield the same matrix

##### Inverse and Transpose
- Let there be matrices $\bf{A, B}$. If $\bf{BA} = \bf{I} = \bf{AB}$, then $\bf{B}$ is the inverse matrix of $\bf{A}$. The inverse matrix of any matrix $\bf{C}$ is denoted by $\bf{C}^{-1}$.
- Not all matrices have an inverse. Matrices with this property are regular/nonsingular while those without are singular.
- For a $2 \times 2$ matrix, the determinant is $a_{11}a_{22}-a_{12}a_{21}$. 
- The inverse of a matrix $\bf{A}^{-1} = \frac{1}{\text{determinant}}\begin{bmatrix}a_{22} & -a_{12} \\ -a_{21} & a_{11}\end{bmatrix}$
- The transpose of a matrix $\bf{A}$ is denoted by $\bf{A}^T$. In $\bf{A}^T$, element a_{ij} correponds to element a_{ji} of $\bf{A}$. Let B 