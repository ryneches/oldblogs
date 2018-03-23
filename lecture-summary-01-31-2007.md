Title: Lecture Summary 01/31/2007
Date: 2007-01-31 16:57:15
Category: general
Slug: lecture-summary-01-31-2007
Author: Russell Neches
Tags: physics, school
Summary: 


Today's lecture covered hyperfine the splitting of hydrogen energy
levels and a rough first-order examination of multi-electron atoms.

### Hyperfine Splitting

Hyperfine splitting is the effect on the electron energy levels due to
the proton's (small) dipole moment. This dipole moment establishes a
weak magnetic field, which interacts with the magnetic field due to the
electron's spin. This effect is different from spin-orbit coupling;
spin-orbit effects are due to the interaction of the electron dipole
moment with the magnetic field arising from the changing *electric*
field seen in the electron's rest frame. Hyperfine splitting is caused
by the direct interaction of the proton and electron magnetic moments.

We are particularly interested in the effect on the ground state. Abers
uses a somewhat impenetrable tensor approach to this problem. Griffiths
uses a much more intuitive approach (though I'm sure it sacrifices
something that the business with the tensors does not -- probably some
generality). I couldn't follow what Abers was doing in lecture, so I
read chapter 6.5 in Griffiths.

Using first order perturbation theory, one obtains a formula for the
correction to the energy that requires the computation of two
expectation values (Griffiths, equation 6.87). However, in the ground
state, or any state with *l*=0, the wave function is spherically
symmetric. The first expectation value vanishes, and the second one can
be computed with a simple triple integral in spherical coordinates.

From this, we obtain an equation for the first order correction to the
energy that is proportional to the expectation value of the scalar
product of the proton spin and the electron spin. Griffiths dubs this
spin-spin coupling to contrast it with spin orbit coupling, which has a
first order energy correction proportional to the expectation value of
the electron spin and the electron orbital angular momentum.

It is important to examine the properties of this Hamiltonian. By
inspection, one can see that that the orbital angular momentum, the
proton spin and the electron spin all *fail* to commute with the
Hamiltonian. However, an operator constructed from the sum of all three
*does* commute. It is not difficult to see why; in the presence of
spin-orbit coupling and spin-spin coupling, a rotation performed on the
proton, the electron, or the electron orbit will each change the
*energy* of the system.

In the ground state the orbit is spherically symmetric, so rotations of
the orbital angular momentum will not change anything. So, in our
consideration of the effect on the ground state, we can discard the
terms relating to the orbital angular momentum. The operator that
commutes with the Hamiltonian is **S**=**S**~e~+**S**~p~. This operator
implies two configurations for the proton and electron spins: In the
"triplet" state, the spins are parallel, the total spin is 1, and the
eigenvalue of **S**^2^ is two h-bar squared (Oh, how I wish I could use
LaTeX in blog posts). In the "singlet" state, the total spin is 0, and
the eigenvalue is 0.

Plugging these expectation values back into the first order correction
for the energy, we can calculate the hyperfine splitting of the ground
state energy level. The triplet state elevates the energy by +1/4 (and
some constants), and the singlet state depresses the energy by -3/4 (and
some constants).

All electrons and all protons have an intrinsic spin, and thus a
magnetic moment. Thus, all hydrogen atoms exhibit this feature. The
exact degenerate ground state never, in fact, occurs. All ground-state
hydrogen atoms are either in the singlet state or the triplet state.
Because the triplet state has an elevated energy, there is a nonzero
probability that it will decay into the singlet state. Taking the energy
released by this transition and (by dividing by Plank's constant)
calculating the frequency of a photon with this energy, you will find
that the frequency is 1420 MHz, or a wavelength of 21 cm. This is the
"21-centimeter line," the most abundant form of electromagnetic
radiation in the universe. This band of microwave emission is one of the
principle diagnostic tools of radio astronomy.

### Multi-electron Systems

We then set aside our beloved hydrogen atom and began examining
multi-electron systems. The zero-order approach is to ignore both
magnetic effects and the electrostatic interaction among the electrons.
One simply adds the Hamiltonians for each electron together. We used
this method to calculate the (very approximate) ground state energies of
helium and a few helium-like ions. This rough approach seems to come
withing about 25% of the observed energies.

To do better, we're going to need a new approximation technique. We'll
save that for Monday, though.
