# Chapter 2
# Convex Sets (Part I)

## Affine and convex sets

Suppose $x_1 \neq x_2$ are two points in $\mathbb{R}^n$, then points of the form $y = \theta x_1 + (1-\theta)x_2$ where $\theta \in \mathbb{R}$ form the $\textit{line}$ passing through $x_1$ and $x_2$. Values of the parameter $\theta$ between $0$ and $1$ correspond to the (closed) $\textit{line segment}$ between $x_1$ and $x_2$. 

Expressing $y$ in the form $y=x_2 + \theta(x_1 - x_2)$ gives the interpretation that $y$ is the sum of the $\textit{base point} \: x_2$ and the direction $x_1 - x_2$ scaled by the parameter $\theta$. 

A set $C \subseteq \mathbb{R}^n$ is $\textit{affine}$ if the line through any two distinct points in $C$ lies in $C$, i.e. for any $x_1, x_2 \in C \: \text{and} \: \theta \in R$ we have $\theta x_1 + (1-\theta) x_2 \in C$. So, $C$ contains the linear combination of any two points in C, provided the coefficients in the linear combination sum to one.

When generalized to more than two points, we refer to these points as an $\textit{affine combination}$ of the points $x_1, \cdots, x_k$. If $C$ is an affine set and $x_0 \in C$, then the set $V = C - x_0 = \{x - x_0 | x \in C\}$ is a subspace or is closed under sums and scalar multiplication. The definition of the $\textit{dimension}$ of an affine set $C$ as the dimension of the subspace $V = C - x_0$, where $x_0$ is any element of C. 

Example 2.1 
$\textit{Solution set of linear equations}$. The solution set of a system of equations $C = \{x | Ax = b \}$, where $A \in \mathbb{R}^{m \times n}$ and $b \in \mathbb{R}^m$ is an affine set. 

The nullspace of $A$, denoted as $null(A)$ is defined as $null(A) = \{z \in \mathbb{R}^n | Az = 0 \}$ which is a subspace as it is closed under sums and scalar multiplication and contains the zero vector. Thus, given that $x_p$ is a particular solution in $C$ such that $Ax_p = b$, then any $x \in C$ can be expressed as $x = x_p + z$ where $z \in null(A)$. The nullspace describes the subspace in which you can move all "directions" from $x_p$ without changing $b$. 

We also have a converse: every affine set can be expressed as the solution set of a system of linear equations. The set of all affine combinations of points in some set $C \subseteq \mathbb{R}^n$ is called the $\textit{affine hull}$ of $C$ and denoted aff $C$. The affine hull is the smallest affine set that contains $C$, in the following sense: if S is any affine set with $C \subseteq S$, then aff $C \subseteq S$. 

The $\textit{affine dimension}$ of a set $C$ is the dimension of its affine hull. Note that, in $\mathbb{R}^2$, the affine hull of the unit circle is all of $\mathbb{R}^2$ because you can draw lines through any pair of points on the circle, and those lines span the entire plane. Thus, the affine dimension of the unit circle is 2, because its affine hull is $\mathbb{R}^2$. The intrinsic dimension of a set refers to the dimension of the set as viewed "within itself," without reference to the embedding space. The unit circle is a 1-dimensional manifold: locally, it looks like a line (you can parametrize it by a single variable, such as the angle or arc length). By most definitions of topological or intrinsic dimension, the unit circle in $\mathbb{R}^2$ has dimension one. 

If the affine dimension of a set $C \subseteq \mathbb{R}^n$ is less than $n$, then the set lies in the affine set aff $C \neq \mathbb{R}^n$. We define the $\textit{relative interior}$ of the set $C$ denoted relint C as its interior relative to aff $C$. 

relint $C = \{x \in C | B(x,r) \cap \text{aff} \: C \subset C \: \text{for some} \: r > 0 \} $

where $B(x, r) = \{y | \: ||y-x|| \leq r\}$, the ball of radius $r$ and center $x$ in the norm $|| \cdot ||$. We can then define the $\textit{relative boundary}$  of a set $C$ as cl $C$ \ relint $C$, where cl $C$ is the closure of C.

Example 2.2
Consider a square in the $(x_1, x_2)$-plane in $R^2$ defined as $C = \{ x \in \mathbb{R}^3 | -1 \leq x_1 \leq 1, -1 \leq x_2 \leq 1, x_3 = 0 \}$
It's affine hull is the $(x_1, x_2)$-plane i.e. aff $C = \{ x \in \mathbb{R}^3 | x_3 = 0 \}$ This is because the interior of a set in a space is the set of points that have a neighborhood entirely contained within the set. For every $C$, every point satisfies $x_3 = 0$ and so the square is flat in the $(x_1, x_2)$-plane. Any neighborhood of a point in $C$ extends into the $x_3$-direction, where $C$ has no points, therefore $C$ has no interior points in $R^3$ making its interior empty. 

The relative interior of a set is the interior of the set relative to its affine hull. The affine hull of $C$ is the smallest affine space containing $C$ which is the plane $\{ x \in \mathbb{R}^3 | x_3 = 0 \}$. Relative to this affine hull, $C$ is a 2D square, and its relative interior consists of all points strictly inside the square

relint $C = \{x \in \mathbb{R}^3 | -1 < x_1 < 1, -1 < x_2 < 1, x_3 = 0 \}$

These points have neighborhoods (in the affine hull) that are entirely contained in $C$, so the relative interior is nonempty. Its boundary (in $\mathbb{R}^3$) is itself; its relative boundary is the wire-frame outline $\{x \in \mathbb{R}^3 | \max \{|x_1|, |x_2|\} = 1, x_3 = 0 \}$, 

A set $C$ is $\textit{convex}$ if the line segment between any two points in $C$ lies in $C$ i.e., if for any $x_!, x_2 \in C$ and any $\theta$ with $0 \leq \theta \leq 1$, we have $\theta x_1 + (1-\theta) x_2 \in C$. Thus, every affine set is also convex since it contains the entire line between any two distinct points in it and therefore also the line segment between the poins. 

A set is convext iff it contains every convex combination of its points. A convex combination of points can be though of as a $\textit{mixture}$ or $\textit{weighted average}$ of the points. The $\textit{convex hull}$ of a set $C$, denoted conv $C$ is the set of all convex combinations of points in $C$ and it is the smallest convex set that contains C. If $B$ is any convex set that contains $C$ then conv $C \subseteq B$.

Convex combinations can include infinite sums, probability distributions and integrals. Suppose $\theta_1, \theta_2, \cdots$ satisfy

$\theta_i \geq 0, i = 1, 2, \cdots,$ and $x_1, x_2, \cdots \in C$ where $C \subseteq \mathbb{R}^n$ is convex
$\sum_{i=1}^{\infty} \theta_i = 1$ then,

$$ \sum_{i=1}^{\infty} \theta_i x_i \in C $$

if the series converges. This can be generalized to probability distributions as well with $\int_C p(x) dx = 1$, where $C \subseteq \mathbb{R}^n$ is convex, then

$$ \int_C p(x) x dx \in C $$

## Cones

A set $C$ is called a $\textit{cone}$ or $\textit{nonnegative homogenous}$, if for every $x \in C$, and $\theta \geq 0$ we have $\theta x \in C$. A set $C$ is a convex cone if it is convex and a cone, which means that for any $x_1, x_2 \in C$ and $\theta_1, \theta_2 \geq 0$ we have $\theta_1 x_1 + \theta_2 x_2 \in C$. This can be visualized geometrically as a two-dimensional pie slive with apex 0 and edges passing through $x_1$ and $x_2$. 

If $x_i$ are in a convex cone $C$, then every conic combination of $x_i$ is in $C$. Conversely, a set $C$ is a convex cone iff it contains all conic combinations of is elements. 

The idea of conic combination can be generalized to infinite sums and integrals. The $\textit{conic hull}$ of a set C is the set of all conic combinations of points in $C$. 

Note that:
- The empty set $\emptyset$, any singleton and the whole space $\mathbb{R}^n$ are affine (hence, convex) subsets of $\mathbb{R}^n$.
- Any line is affine. If it passes through zero, it is a subspace hence also a convex cone. 

A line can be written as $\{x_0 + \theta v | \theta \in \mathbb{R} \}$ where $x_0$ is a point on the line and $v \neq 0$ is the direction vector. This satisfies the definition of an affine set since any affine combination of points on the line is also on the line. If the line passes through the origin ($x_0 = 0$) then it becomes $\{ \theta v | \theta \in \mathbb{R} \}$, which is a subspace of $\mathbb{R}^n$. Subspaces are affine and also convex cones (since they are closed under linear combinations with nonnegative coefficients)

- A line segment is convex but not affine

A line segment can be written as $\{ x_1 + \theta(x_1 - x_2) | 0 \leq \theta \leq 1 \}$ where $x_1$ and $x_2$ are endpoints. It is convex because any line segment between two points in the set lies entirely in the set. The line segment is not affine as affine combinations allow $\theta$ to take any real value ($\theta \in \mathbb{R}$), which means extending beyond $[0, 1]$.

- A $\textit{ray}$ which has the form $\{x_0 + \theta v | \theta \geq 0 \}$, where $v \neq 0$ is convex, but not affine. It is a convex cone if its base $x_0$ is 0. 

A ray is convex because any convex combination of two points on the ray lies on the ray. It is not affine because it is not closed under negative scalar multiplication. A ray is a convex cone if its base $x_0 = 0$ since in that case it is closed under positive scalar multiplication.

- Any subspace is affine, and a convex cone. 

A subspace is closed under linear combinations, and thus, by definition, it is affine. A subspace is closed under scalar multiplication, including nonnegative scalars, making it a convex cone.

## Hyperplanes and halfspaces

A $\textit{hyperplane}$ is a set of the form $\{ x | a^Tx = b \}$, where $a \in \mathbb{R}^n$, $a \neq 0$ and $b \in \mathbb{R}$ and can be interpreted as the set of points with a constant inner product to a given vector $a$, or as a hyperplane with $\textit{normal vector}$ $a$; the constant $b \in \mathbb{R}$ determines the offset of the hyperplane from the origin. This geometric interpretation can be understood by expressing the hyperplane in the form

$$\{ x \: | \: a^T(x - x_0) = 0 \}$$

where $x_0$ is any point in the hyperplane or any point that satisfies $a^Tx_0 = b$ and can be expressed as

$$\{ x \: | \: a^T(x-x_0) = 0 \} = x_0 + a^{\perp} $$

where $a^\perp$ denotes the orthogonal complement of $a$ or the set of all vectors orthogonal to it, $a^\perp =\{ v \: | \: a^Tv = 0 \}$. This shows that the hyperplane consists of an offset $x_0$, plus all vectors orthogonal to the (normal) vector $a$. A hyperplane divides $\mathbb{R}^n$ into two $\textit{halfspaces}$. A closed halfspace is a set of the form $\{x \: | \: a^Tx \leq b\}$ where $a \neq 0$. Halfspaces are convex, but not affine. 

The halfspace can also be expressed as $\{ x \: | \: a^T(x - x_0) \leq 0 \}$ where $x_0$ is any point on the associated hyperplane i.e. satisfies $a^Tx_0 = b$ which suggests that the halfspace consists of $x_0$ plus any vector that makes an obtuse (or right) angle with the (outward normal) vector $a$. The boundary of the halfspace is the hyperplane $\{ x \: | \: a^Tx=b \}$. The set $\{x \: | \: a^Tx < b \}$ is the interior of the halfspace $\{x \: | \: a^Tx \leq b\}$ and is called an $\textit{open halfspace}$.

## Euclidean balls and ellipsoids

A Euclidean ball in $\mathbb{R}^n$ has the form

$$ B (x_c, r) = \{ x \: | \: ||x-x_c||_2 \leq r\} = \{x \: | \: (x-x_c)^T(x-x_c) \leq r^2 \} = \{x_c + ru \: | \: ||u||_2 \leq 1 \} $$

where $r > 0$ and $|| \cdot ||_2$ denotes the Euclidean norm i.e. $||u||_2 = (u^Tu)^{1/2}$. 

A Euclidean ball is a convex set which can be proven using the homogeneity property and triangle inequality for the Euclidean norm with $||x_1 - x_c||_2 \leq r$, $||x_2 - x_c||_2 \leq r$ and $0 \leq \theta \leq 1$ then

$$ ||\theta x_1 + (1-\theta) x_2 - x_c ||_2 = ||\theta (x_1 - x_c) + (1-\theta)(x_2-x_c)||_2 $$
$$ \leq \theta ||x_1 - x_c||_2 + (1-\theta) ||x_2 - x_c||_2 \leq r$$

$\textit{Ellipsoids}$ are a related family of convex sets which have the form

$$ \Epsilon = \{x \: | \: (x-x_c)^TP^{-1}(x-x_c) \leq 1 \}$$

where $P = P^T \succ 0$ i.e. P is symmetric and positive definite with vector $x_c$ at the center of the ellipsoid. The matrix $P$ determines how far the ellipsoid extends in every direction from $x_c$. The lengths of the semi-axes of $\Epsilon$ are given by $\sqrt{\lambda_i}$ where $\lambda_i$ are the eigenvalues of $P$. 

A ball is an ellipsoid with $P = r^2I$ and another common representation of an ellipsoid is $\Epsilon = \{x_c + Au \: | \: ||u||_2 \leq 1 \}$ where $A$ is square and nonsingular. We can assume here that $A$ is symmetric and positive definite. When $A$ is symmetric positive semidefinite but singular, the set is called a $\textit{degenerate ellipsoid}$ where its affine dimension is equal to the rank of $A$. 

## Norm balls and norm cones

We can show that a $\textit{norm ball}$ of radius $r$ and center $x_c$ and given by $\{x \: | \: ||x-x_c|| \leq r \}$ is convex. The $\textit{norm cone}$ associated with the norm $|| \cdot ||$ is the set

$$ C = \{(x, t) | ||x|| \leq t\} \subseteq \mathbb{R}^{n+1} $$

which is a convex cone. 

Example 2.3
The $\textit{second-order cone}$ is the norm cone for the euclidean norm which is also called the $\textit{Lorentz cone}$ and it is defined by a quadratic inequality.

## Polyhedra

A $\textit{polyhedron}$ is defined as the solution set of a finite number of linear equalities and inequalities:

$$ P = \{ x \: | \: a_j^Tx \leq b_j, j = 1,\cdots,m, c_j^Tx = d_j, j = 1,\cdots,p \} $$

and is thus the intersection of a finite number of halfspaces and hyperplanes. Affine sets, rays, line segments and halfspaces are all polyhedra. We can also use the compact notation

$$ P = \{ x \: | \: Ax \preceq b,  Cx = d\} $$

where

$$A = \begin{bmatrix} a_1^T \\ \vdots \\ a_m^T \end{bmatrix}, C = \begin{bmatrix} c_1^T \\ \vdots \\ c_p^T \end{bmatrix}$$

## Simplexes

$\textit{Simplexes}$ are another important family of polyhedra. Suppose the $k+1$ points $v_0, \cdots, v_k \in \mathbb{R}^n$ are $\textit{affinely independent}$, which means $v_1 - v_0, \cdots, v_k - v_0$ are linearly independent. The simplex determined by them is given by

$$C = \text{conv}(v_0, \cdots, v_k) = \{\theta_0v_0 + \cdots + \theta_kv_k \: | \: \theta \succeq 0, 1^T\theta = 1 \}$$

The affine dimension of the simplex is $k$, so it is sometimes referred to as a $k$-dimensional simplex in $\mathbb{R}^n$. We can define this as a polyhedron by looking at the definition, $x \in C$ if and only if $x = \theta_0v_0 + \theta_1v_1 + \cdots + \theta_kv_k$ for some $\theta \succeq 0$ with $1^T\theta = 1$. If we define $y = (\theta_1, \cdots, \theta_k)$ and 

$$B = [v_1 - v_0 \cdots v_k - v_0 ] \in \mathbb{R}^{n \times k}$$

we can say that $x \in C$ iff $x = v_0 + By$ for some $y \succeq 0$ with $1^Ty \leq 1$. The affine independence of $v_0, \cdots, v_k$ implies that $B$ has rank $k$. By definition, then, there exists a nonsingular matrix $A = (A_1, A_2) \in \mathbb{R}^{n \times n}$ such that

$$AB = \begin{bmatrix} A_1 \\ A_2 \end{bmatrix} \: B = \begin{bmatrix} I \\ 0 \end{bmatrix}$$

Multiplying $x$ on the left with $A$, we obtain $A_1 x = A_1 v_0 + y$ and $A_2 x = A_2 v_0$ which gives that $x \in C$ iff $A_2x = A_2v_0$ and the vector $y = A_1x - A_1v_0$ satisfies $y \succeq 0$ and $1^Ty \leq 1$

Note, the convex hull of the finite set $\{ v_1, \cdots, v_k\}$ us

$$\text{conv}\{v_1, \cdots, v_k\} = \{\theta_1v_1 + \cdots + \theta_kv_k\ | \theta \succeq 0, 1^T\theta = 1\}$$

is a polyehedron and bounded by a set of linear equalities and inequalities. 

Consider the unit ball in $l_{\infty}$-norm in $\mathbb{R}^n$

$$ C = \{x \: | \: |x_i| \leq 1, i = 1, \cdots, n\}$$
The set $C$ can be described with $2n$ linear inequalities. We require $2^n$ vectors to describe it in the convec hull as $C = \text{conv}\{v_1,\cdots,v_{2^n}\}$ where $v_1,\cdots,v_{2^n}$ are the $2^n$ vectors all of whose components are $1$ or $-1$. 

## The positive semidefinite cone

Let $S^n$ denote the set of symmetric $n \times n$ matrices

$$S^n = \{X \in \mathbb{R}^{n \times n} | X = X^T\} $$

which is a vector space with dimension $n(n+1)/2$. The notation $S^n_{+}$ to denote the set of symmetric positive semidefinite matrices and $S^n_{++}$ to denote the set of symmetric positive definite matrices

$$S^n_{+} = \{ X \in S^n \: | \: X \succeq 0 \}, $$
and
$$S^n_{++} = \{ X \in S^n \: | \: X \succ 0 \} $$

The set $S^n_{+}$ is a convex cone which can be seen directly from the definition of positive semidefiniteness, for any $x \in \mathbb{R}^n$ and $\theta_1, \theta_2 \geq 0$ and $A, B \in S^n_{+}$ we have

$$ x^T(\theta_1 A + \theta_2 B)x = \theta_1 x^T Ax + \theta_2 x^T Bx \geq 0 $$