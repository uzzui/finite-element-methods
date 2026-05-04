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

## Formulação variacional

A formulação variacional consiste em encontrar $u_h \in W_h$ tal que

$$
\int_{-2}^{2} u_h'(x)v_h'(x)\,dx
=
\int_{-2}^{2}\pi^2\sin(\pi x)v_h(x)\,dx
+
(\pi+1)v_h(2),
\qquad \forall v_h \in V_h.
$$

com a condição de Dirichlet

$$
u_h(-2)=1.
$$

## Discretização

A malha uniforme é dada por

$$
x_i = -2 + ih, \qquad h=0.5, \qquad i=0,1,\dots,8.
$$

Logo, os nós são

$$
-2,\,-1.5,\,-1,\,-0.5,\,0,\,0.5,\,1,\,1.5,\,2.
$$

São utilizados elementos finitos lineares de Lagrange, isto é, funções contínuas em $[-2,2]$ e lineares em cada elemento da malha.
