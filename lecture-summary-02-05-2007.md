Title: Lecture Summary 02/05/2007
Date: 2007-02-05 15:09:36
Category: general
Slug: lecture-summary-02-05-2007
Author: Russell Neches
Tags: physics, school
Summary: 


Today, we started out by examining the zeroth and first order
perturbational solution to the two-electron problem (H^-^, He, Li^+^,
and so on). The perturbation is fairly simple (it's just repeated cases
of the Coulomb potential), but for multiple electrons, results in a
fairly nasty integral over six dimensions. Much of the first half of the
class was devoted to a technique for solving this integral. I wrote down
the technique, but I don't anticipate needed to learn it. The solution
is in the book, and the technique is much too complicated to appear in a
test question. It looked useful, so I'll study it later when I have more
time.

We then calculated the energies of various two electron systems. It was
noted that the perturbational approach seems to converge very slowly,
and that the second order calculation would be a nightmare. Onwards to
variational methods!

We then rushed through an introduction to the variational method. The
variational method can be thought of as a generalization of perturbation
theory, but only for the ground state. It works as follows: You assume
*a priori* that there is an eigenstate of the Hamiltonian with a minimum
energy, and you make a guess about what it might be (this only works if
your guess is "reasonable"). The "true" ground state will be the
eigenfunction that minimizes the energy. So, you guess its form, and
tweak whatever parameters it has until you find the minimum energy. If
you guessed the exact form of the function, and you do enough tweaking,
in theory you can find the exact eigenfunction.

A little more formally, you know that each eigenstate spans all of
function space. So, the ground state will span all of function space.
So, whatever you guess, it must be a linear combination of the
eigenstates. So, you write the trial function as a sum over the
eigenfunctions with some coefficient for each one (you can always do
this). Each eigenstate corresponds to an energy eigenvalue, so you can
replace the sum over eigenfunctions with a sum over their corresponding
energies (and their coefficients). As you vary your trial functions and
evaluate the sum, the lowest possible value you can find will be the
case where the coefficient of the ground state is 1, and 0 for all the
others.
