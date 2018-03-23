Title: Lecture Summary 01/29/2007
Date: 2007-01-29 15:13:49
Category: general
Slug: lecture-summary-01-29-2007
Author: Russell Neches
Tags: physics, school
Summary: 


### Spin-Orbit Coupling

Today's lecture covered the spin-orbit coupling of the hydrogen atom.
This phenomenon is due to the fact that because the electron has an
intrinsic spin, it also has a finite magnetic moment. Because the
electron is in motion, the magnetic moment couples with the
proton-electron electric field.

One can think of the situation this way; most of the electron's motion
is dominated by the fact that it has an electric charge *-e*, but some
small part of the motion is due to the fact that there is a little
magnet bolted onto the charge. A magnet at rest in a constant electric
field suffers no force, but a magnet in motion in an electric field (or
a stationary magnet in a changing electric field) does suffer a force.

If we pretend that the electron is moving slowly enough (i.e., that it
is perfectly non-relativistic), you can do a classical
frame-of-reference change such that the electron is at rest, and the
proton is moving. If the electron was moving with velocity **v**, then
in the electron frame, the proton is moving with velocity -**v**. We can
then use the Biot-Savart law to find the magnetic field seen by the
electron rest frame. Taking the dot product of this magnetic field with
the electron's magnetic moment gives us the magnetic energy.

Sort of, anyway. The actual observed magnetic energy is half of what one
obtains by this means. The reason for this factor-of-two error is that
we relied on classical assumptions when we transformed into the
accelerated frame of reference of the electron. Using the correct
transformation yields the right coefficients. However, the classical
result is correct to within a constant factor, which can be determined
by observation anyway. So. Ahem. Moving on.

We can now take the magnetic energy and treat it as a perturbation on
the Hamiltonian for the elementary hydrogen problem. The usual process
applies. The result, to first order, can be found in section 7.3.2 of
Abers' book.

### The Relativistic Kinetic Energy Correction

This result is still wrong. We actually made *two* erroneous classical
assumptions. The matter of the accelerated reference frame has been
addressed (albeit in a completely unsatisfactory way). The first
erroneous assumption was that the electron orbital velocity is slow. In
fact, it is roughly 1% the speed of light, and thus relativistic effects
are first order corrections.

This requires replacing the classical Hamiltonian of the electron with
the correct relativistic Hamiltonian. We can expand in powers of the
momentum, and keeping the first and second order result. Again, we treat
this using perturbation theory.

### The Fine Structure of the Hydrogen Atom

Taking the results of the spin-orbit coupling and the relativistic
kinetic energy corrections together gives us the fine structure
correction to the spectrum of the hydrogen atom. The fine structure
correction depends on *n* (the energy level) and *j* (the electron spin
orientation), but not *l* (the orbital angular momentum). This is where
the fine structure constant alpha gets its name.
