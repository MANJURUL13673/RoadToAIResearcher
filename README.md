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
