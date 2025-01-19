# Chapter 2
# Convex Sets

## Affine and convex sets

Suppose $x_1 \neq x_2$ are two points in $\mathbb{R}^n$, then points of the form $y = \theta x_1 + (1-\theta)x_2$ where $\theta \in \R$ form the $\textit{line}$ passing through $x_1$ and $x_2$. Values of the parameter $\theta$ between $0$ and $1$ correspond to the (closed) $\textit{line segment}$ between $x_1$ and $x_2$. 

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