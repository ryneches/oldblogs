Title: Lecture Summary 01/21/2007
Date: 2007-01-22 15:42:00
Category: general
Slug: lecture-summary-01-21-2007
Author: Russell Neches
Tags: 
Summary: 


To make sure I pay attention in class, I've decided to write summaries
of each lecture. This lead immediately to the oddly difficult question
of where to put them. Should I write them in my notebook? Write them on
my computer at school? Scrawl them on the wall of the men's room? Since
I have this blog thing that will otherwise go mostly unused this
quarter, I decided to write them here. That way, maybe people will
notice if I slack off, and admonish me. So, lectures are on Monday and
Wednesday. If you see that a summary is missing, you can help me keep
the slack away by sending me a finger-wagging email.

Today Abers covered sections 7.1.1, 7.1.2 and 7.2.1 in his book. They
are as follows.

Introduction to bound-state perturbation theory
-----------------------------------------------

Generally, one uses bound-state perturbation theory to solve problems
that don't have exact solutions, but are very close to problems that do
have exact solutions. If you can represent something as a problem with
an exact solution plus some small wiggle, you can use perturbation
theory. For example, the infinite square well potential has an exact
solution. The infinite square well with a lump at the bottom probably
doesn't, but is probably amenable to perturbation theory.

The process goes like this :

-   Write the Hamiltonian as the sum of the unperturbed Hamiltonian and
    some $H'$, which is small (we hope).
-   Note that the presence of the H' will change the energy eigenvalue,
    hopefully by some small amount. Call this delta.
-   We want to solve for delta. It is usually not possible to do this
    directly. However, we can get a zeroth-order approximation of delta
    by taking the expectation value of the *perturbed* Hamiltonian H'
    with the *unperturbed* eigenstate. The error will be one order
    higher.
-   To get the higher order terms, we need to expand the state vector
    (*the* state vector, not the unperturbed state vector) in powers of
    H' (or its matrix elements, if that makes any sense). Equation 7.8
    in Abers does the job.
-   Successive iterations of the process yields successfully higher
    order terms.
-   Care must be given to the normalization of the perturbed
    eigenstates; different books (e.g. Griffiths) use slightly different
    conventions.

The perturbation method has two restrictions:

1.  There must be a one-to-one correspondence between eigenstates of the
    unperturbed Hamiltonian and the eigenstates of the full Hamiltonian.
2.  There is a second restriction, explained incoherently in the book
    and mysteriously in today's lecture, that has something to do with
    how one handles degeneracies.

Perturbation of the first excited state of Hydrogen
---------------------------------------------------

We went through the derivation of the energy splitting due to the
presence of a weak electric field (the Stark effect). There was much
confusion resulting from the change in bases required to avoid dividing
by zero when evaluating the formula for obtaining the first order terms.
Abers noted that many textbooks treat "degenerate" perturbation theory
separately, and that this was silly because all you had to do was switch
into a basis that diagonalizes $H'$, find the higher order terms, and then
switch back into the original basis.

However, by the time we had returned from our basis-changing digression,
it was rather unclear what had happened. Fortunately, it seemed to work,
and we calculated something for the energy shift in terms of the energy
eigenstates.

To solve for the shift directly, we integrated over all space in
spherical coordinates. As usual, the spherical harmonics are separable,
and the result for the perturbed radial wave function is -3\*sqrt(3)a,
where a is the Bohr radius. The energy shift is -3\*e\*E\*a.
