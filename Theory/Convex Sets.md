---
title:  "Convex Sets"
date:   2025-01-19
mathjax: true
---

# Chapter 2
# Convex Sets

## Affine and convex sets

Suppose $x_1 \neq x_2$ are two points in $\R^n$, then points of the form $y = \theta x_1 + (1-\theta)x_2$ where $\theta \in \R$ form the $\textit{line}$ passing through $x_1$ and $x_2$. Values of the parameter $\theta$ between $0$ and $1$ correspond to the (closed) $\textit{line segment}$ between $x_1$ and $x_2$. 

Expressing $y$ in the form $y=x_2 + \theta(x_1 - x_2)$ gives the interpretation that $y$ is the sum of the $\textit{base point} \: x_2$ and the direction $x_1 - x_2$ scaled by the parameter $\theta$. 

A set $C \subseteq \R^n$ is $\textit{affine}$ if the line through any two distinct points in $C$ lies in $C$, i.e. for any $x_1, x_2 \in C \: \text{and} \: \theta \in R$ we have $\theta x_1 + (1-\theta) x_2 \in C$. So, $C$ contains the linear combination of any two points in C, provided the coefficients in the linear combination sum to one.

When generalized to more than two points, we refer to these points as an $\textit{affine combination}$ of the points $x_1, \cdots, x_k$. If $C$ is an affine set