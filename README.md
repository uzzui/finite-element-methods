# Exercício 1 — Método dos Elementos Finitos

Este repositório contém a implementação em Python, em formato de notebook, do problema variacional associado a um problema de Poisson unidimensional com condição de Dirichlet em $x=-2$ e condição de Neumann em $x=2$.

## Enunciado

Seja $\Omega = (-2,2)$. Considere o problema de encontrar uma função $u:\Omega \to \mathbb{R}$ suficientemente regular que satisfaça

$$
u''(x) = -\pi^2 \sin(\pi x), \qquad x \in \Omega,
$$

com condições de contorno

$$
u(-2)=1,
$$

e

$$
u'(2)=\pi+1.
$$

A solução exata do problema é

$$
u(x)=\sin(\pi x)+x+3.
$$

## Objetivo

O objetivo é implementar, usando o Método dos Elementos Finitos com funções lineares por elemento, a formulação variacional em dimensão finita associada ao problema acima, considerando uma malha uniforme com passo $h=0{,}5$.
