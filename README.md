# RoadToAIResearcher [Semiconductor Metrology]

## Linear Algebra

### Vectors

#### Addition

```math
\begin{bmatrix} x_1 \\ y_1 \end{bmatrix} + \begin{bmatrix} x_2 \\ y_2 \end{bmatrix} = \begin{bmatrix} x_1 + x_2 \\ y_1 + y_2 \end{bmatrix}
```

#### Scaling

```math
c \begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} c \cdot x \\ c \cdot y \end{bmatrix}
```
### Matrices

#### Linear Transformation

Linear transformations move space around so that gridlines stay parallel and evenly spaced, and the origin stays fixed. The columns of the matrix tell you where the basis vectors land.

2D transformation:

```math
\begin{bmatrix} a & b \\ c & d \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} a x + b y \\ c x + d y \end{bmatrix}
```

3D transformation:

```math
\begin{bmatrix} a & b & c \\ d & e & f \\ g & h & i \end{bmatrix} \begin{bmatrix} x \\ y \\ z \end{bmatrix} = \begin{bmatrix} a x + b y + c z \\ d x + e y + f z \\ g x + h y + i z \end{bmatrix}
```

#### Matrix Multiplication

Each entry of the result is the dot product of a row from the left matrix with a column from the right.

```math
\begin{bmatrix} a & b \\ c & d \end{bmatrix} \begin{bmatrix} e & f \\ g & h \end{bmatrix} = \begin{bmatrix} a e + b g & a f + b h \\ c e + d g & c f + d h \end{bmatrix}
```

#### Determinant

The determinant is the factor by which a transformation scales area (2D) or volume (3D). It is only defined for square matrices (rows = columns).

2×2:

```math
\det \begin{bmatrix} a & b \\ c & d \end{bmatrix} = ad - bc
```

3×3:

```math
\det \begin{bmatrix} a & b & c \\ d & e & f \\ g & h & i \end{bmatrix} = a(ei - fh) - b(di - fg) + c(dh - eg)
```

#### Inverse Matrices

#### Inverse Matrix

The inverse $A^{-1}$ undoes the transformation $A$, so that $A A^{-1} = I$ (the identity matrix). It exists only for square matrices with a nonzero determinant.

```math
A A^{-1} = A^{-1} A = I
```

For a 2×2 matrix:

```math
\begin{bmatrix} a & b \\ c & d \end{bmatrix}^{-1} = \frac{1}{ad - bc} \begin{bmatrix} d & -b \\ -c & a \end{bmatrix}
```

For a 3×3 matrix, the inverse is the adjugate (transpose of the cofactor matrix) divided by the determinant:

```math
\begin{bmatrix} a & b & c \\ d & e & f \\ g & h & i \end{bmatrix}^{-1} = \frac{1}{\det(A)} \begin{bmatrix} ei - fh & ch - bi & bf - ce \\ fg - di & ai - cg & cd - af \\ dh - eg & bg - ah & ae - bd \end{bmatrix}
```

A matrix with determinant zero is **singular** and has no inverse.

#### Dot Product

The **dot product** of two vectors produces a single scalar. It can be computed component-wise, or geometrically from the angle between them.

```math
\mathbf{a} \cdot \mathbf{b} = a_1 b_1 + a_2 b_2 + a_3 b_3 = \|\mathbf{a}\| \, \|\mathbf{b}\| \cos\theta
```

It is **zero exactly when the vectors are perpendicular**, making it the standard test for orthogonality. Each entry of a matrix product is itself a dot product of a row with a column.

#### Cross Product

The **cross product** of two 3D vectors produces a new vector perpendicular to both. (It is defined only in three dimensions.)

```math
\begin{bmatrix} a_1 \\ a_2 \\ a_3 \end{bmatrix} \times \begin{bmatrix} b_1 \\ b_2 \\ b_3 \end{bmatrix} = \begin{bmatrix} a_2 b_3 - a_3 b_2 \\ a_3 b_1 - a_1 b_3 \\ a_1 b_2 - a_2 b_1 \end{bmatrix}
```

It can also be written as a determinant with the unit vectors $\mathbf{i}, \mathbf{j}, \mathbf{k}$:

```math
\begin{bmatrix} a_1 \\ a_2 \\ a_3 \end{bmatrix} \times \begin{bmatrix} b_1 \\ b_2 \\ b_3 \end{bmatrix} = \det \begin{bmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ a_1 & a_2 & a_3 \\ b_1 & b_2 & b_3 \end{bmatrix}
```

Its magnitude $\|\mathbf{a}\|\|\mathbf{b}\|\sin\theta$ equals the area of the parallelogram spanned by the two vectors, and it is zero when they are parallel.

#### Cramer's Rule

**Cramer's rule** solves a system $A\mathbf{x} = \mathbf{b}$ using determinants. Each unknown $x_i$ is the determinant of $A$ with its $i$-th column replaced by $\mathbf{b}$, divided by $\det(A)$:

```math
x_i = \frac{\det(A_i)}{\det(A)}
```

For a 2×2 system:

```math
x = \frac{ed - bf}{ad - bc} \qquad y = \frac{af - ec}{ad - bc}
```

It requires $\det(A) \neq 0$ — the same condition under which $A$ is invertible. The rule is elegant but impractical for large systems, where elimination methods are used instead.


**Example.** Solve the system:

```math
\begin{aligned}
2x + y &= 5 \\
x + 3y &= 10
\end{aligned}
```

Write it as $A\mathbf{x} = \mathbf{b}$:

```math
\begin{bmatrix} 2 & 1 \\ 1 & 3 \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} 5 \\ 10 \end{bmatrix}
```

**Step 1 — main determinant** (the shared denominator):

```math
\det(A) = \det \begin{bmatrix} 2 & 1 \\ 1 & 3 \end{bmatrix} = (2)(3) - (1)(1) = 5
```

**Step 2 — solve for $x$** by replacing the first column with $\mathbf{b}$:

```math
x = \frac{\det \begin{bmatrix} 5 & 1 \\ 10 & 3 \end{bmatrix}}{\det(A)} = \frac{(5)(3) - (1)(10)}{5} = \frac{5}{5} = 1
```

**Step 3 — solve for $y$** by replacing the second column with $\mathbf{b}$:

```math
y = \frac{\det \begin{bmatrix} 2 & 5 \\ 1 & 10 \end{bmatrix}}{\det(A)} = \frac{(2)(10) - (5)(1)}{5} = \frac{15}{5} = 3
```

**Solution:** $x = 1$, $y = 3$.

#### Eigenvalues and Eigenvectors

An **eigenvector** of a matrix $A$ is a special vector whose direction is unchanged by the transformation — $A$ only stretches or shrinks it. The scaling factor is its **eigenvalue** $\lambda$.

```math
A \mathbf{v} = \lambda \mathbf{v}
```

To find them, rewrite this as $(A - \lambda I)\mathbf{v} = \mathbf{0}$. A nonzero solution exists only when the matrix is singular, giving the **characteristic equation**:

```math
\det(A - \lambda I) = 0
```

**Example.** For $A = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix}$:

```math
\det \begin{bmatrix} 2 - \lambda & 1 \\ 1 & 2 - \lambda \end{bmatrix} = (2-\lambda)^2 - 1 = 0
```

Solving gives $\lambda = 3$ (eigenvector $\begin{bmatrix} 1 \\ 1 \end{bmatrix}$) and $\lambda = 1$ (eigenvector $\begin{bmatrix} 1 \\ -1 \end{bmatrix}$).