Este repositório contém a implementação em Python, em formato de notebook, do problema variacional associado ao problema de Poisson unidimensional com condição de Dirichlet em \(x=-2\) e condição de Neumann em \(x=2\).

## Enunciado

Seja \(\Omega=(-2,2)\). Considere o problema de encontrar uma função \(u:\Omega\to\mathbb{R}\) suficientemente regular que satisfaça

\[
u''(x)=-\pi^2\sin(\pi x),
\qquad x\in\Omega,
\]

com condições de contorno

\[
u(-2)=1,
\]

e

\[
u'(2)=\pi+1.
\]

A solução exata do problema é

\[
u(x)=\sin(\pi x)+x+3.
\]

O objetivo é, a partir de uma discretização de \(\Omega\) em uma malha regular com elementos de tamanho \(h=0{,}5\), implementar o problema variacional em dimensão finita usando o Método dos Elementos Finitos com funções lineares por elemento.

## Formulação variacional

A formulação variacional consiste em encontrar \(u_h\in W_h\) tal que

\[
\int_{-2}^{2} u_h'(x)v_h'(x)\,dx
=
\int_{-2}^{2}\pi^2\sin(\pi x)v_h(x)\,dx
+
(\pi+1)v_h(2),
\qquad \forall v_h\in V_h.
\]

A condição de Dirichlet impõe

\[
u_h(-2)=1.
\]

## Discretização

A malha uniforme é dada por

\[
x_i=-2+ih,
\qquad h=0{,}5,
\qquad i=0,1,\dots,8.
\]

Assim, os nós são

\[
-2,\ -1{,}5,\ -1,\ -0{,}5,\ 0,\ 0{,}5,\ 1,\ 1{,}5,\ 2.
\]

São utilizados elementos finitos lineares de Lagrange, isto é, funções contínuas em \([-2,2]\) e lineares em cada elemento da malha.

## Implementação

O notebook realiza:

1. construção da malha;
2. montagem da matriz de rigidez global;
3. montagem do vetor de força global;
4. imposição da condição de Dirichlet \(u(-2)=1\);
5. inclusão do termo de Neumann \((\pi+1)v_h(2)\);
6. resolução do sistema linear reduzido;
7. comparação com a solução exata;
8. cálculo do erro nodal;
9. geração do gráfico da solução aproximada e da solução exata.
