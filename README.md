# RoadToAIResearcher [Semiconductor Metrology]

## Linear Algebra
### Vector
1. Addition

$$\begin{bmatrix} x_1 \\\\ y_1 \end{bmatrix} + \begin{bmatrix} x_2 \\\\ y_2 \end{bmatrix} = \begin{bmatrix} x_1 + x_2 \\\\ y_1 + y_2 \end{bmatrix}$$

2. Scaling

$$c \begin{bmatrix} x \\\\ y \end{bmatrix} = \begin{bmatrix} c \cdot x \\\\ c \cdot y \end{bmatrix}$$

3. Linear Transformation
Linear transformation are a way to move around space such that gridline remains parallel and evenly spaced, and such that origin remain fixed.

    2D vector transformation:
```math
\begin{bmatrix} a & b \\ c & d \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} a x + b y \\ c x + d y \end{bmatrix}
```

4. Matrix Multiplication:

```math
\begin{bmatrix} a & b \\ c & d \end{bmatrix} \begin{bmatrix} e & f \\ g & h \end{bmatrix} = \begin{bmatrix} a e + b g & a f + b h \\ c e + d g & c f + d h \end{bmatrix}
```