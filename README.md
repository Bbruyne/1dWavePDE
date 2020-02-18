# 1dWavePDE
This repository contains a code to solve the one dimensional *wave equation* in **Julia**. 

It solves the wave equation (with `v=1m/s`) on the unit interval [0,1] with absorbing boundary conditions (`psi(0,t) = psi(1,t) = 0`).
The state vector contains `psi` (the wave function) and `psidot` (the time derivative of the wave function) as the equation is of second order in time derivative.

Below are several examples of the use of the code. We plot the solution at several times t=0, 1/10 T, 2/10 T, ..., T, where T is the period of the solution.

* initial conditions : `psi(x,0) = sin(pi*x)` and `psidot(x,0) = 0` with `delta_t=10^-2` and `nHats=100` (not respecting CFL convergence conditions)

![Unbiaised](/img/waveBad.PNG)
Format: ![Alt Text](url)

Hence, we see that the solver does not converge to the actual solution.

* initial conditions : `psi(x,0) = sin(pi*x)` and `psidot(x,0) = 0` with `delta_t=10^-5` and `nHats=100` (this time respecting CFL convergence conditions)

![Unbiaised](/img/waveGood.png)
Format: ![Alt Text](url)

where we recognize the solution `psi(x,t)=cos(pi*t) sin(pi*x)`. The solver hence works.

Additionally, we can plot the energy of the wave, defined as the integral of the sum of the squared time derivative and position derivative of the wave function. For the last case, it gives:

![Unbiaised](/img/energyGood.PNG)
Format: ![Alt Text](url)

where we notice that the energy is (almost) conserved over the period.
