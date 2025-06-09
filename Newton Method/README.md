**Newton's Method Explorer** is a Python project that reproduces and extends the functionality of the Mathematica notebook **Newton_method.nb**. It symbolically derives and numerically investigates the “chaotic” iteration patterns of Newton’s method applied to two cubic polynomials:

1. \(f_1(x) = x^3 - x - 1\)  
2. \(g_2(x) = x^3 - x + 1\)  

By composing three successive Newton‐map iterates and examining the resulting polynomial \(Q(x) = x - N(N(N(x)))\), this project reveals fixed points, period‐3 cycles, and bifurcation‐style diagrams known to accompany chaotic dynamical systems.

---

## 🚀 Features

- **Symbolic derivation** of  
  - Newton maps \(N_1(x)\) for \(f_1(x)\)  
  - Newton maps \(N_2(x)\) for \(g_2(x)\)  
  - Third‐iterate composites \(Q_1(x) = x - N_1(N_1(N_1(x)))\) and \(Q_2(x) = x - N_2(N_2(N_2(x)))\).  
- **Factorization** of \(Q_1\) and \(Q_2\), revealing real roots (fixed/period‐3 points).  
- **Numeric exploration**:  
  - **Cobweb plots** showing how Newton’s method moves toward (or away from) roots, for a given starting \(x_0\).  
  - **Bifurcation‐style scatter plots**:
    - Iterate many initial seeds \(x_0\) through 300 Newton steps and plot the final 50 iterates.
    - Visualize “bands” of convergence, period‐n orbits, and chaotic intervals on the real line.  
- **Exportable animations** (GIF or MP4) can be produced from the Python code (optional).
