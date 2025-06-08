Runge-Kutta-Fehlberg (1969): A Method of Integrating Ordinary Differential Equations Using Embedded Formulas of Orders Four and Five.
Adaptive Runge-Kutta-Fehlberg 4(5) Method (RKF45)

This repository contains a Python implementation of the fifth-order Runge-Kutta method with adaptive step-size control using the embedded 4th-order error estimate (RKF45).

## Features
- Adaptive time stepping for error control
- Embedded 4th/5th order method
- Example: exponential decay `dy/dt = -2y`
- Accuracy benchmarked against analytical solution

## Requirements
```bash
pip install numpy matplotlib


# Adaptive Runge-Kutta-Fehlberg Method for Solving ODEs

## Abstract
We implement and test an adaptive numerical method for solving ordinary differential equations using the Runge-Kutta-Fehlberg 4(5) method. The method automatically adjusts the time step to balance efficiency and accuracy.

## Introduction
The RKF45 method offers two key benefits:
1. **High accuracy** with fifth-order precision.
2. **Adaptive step control**, making it suitable for stiff or highly nonlinear ODEs.

## Method
Given an ODE:
\[
\frac{dy}{dt} = f(t, y), \quad y(t_0) = y_0
\]
the RKF45 method evaluates six intermediate stages \( k_1 \) to \( k_6 \) and computes both 4th- and 5th-order approximations. The difference provides an error estimate.

## Error Control and Step Size Update
\[
h_{\text{new}} = 0.84 \left( \frac{\text{tol} \cdot h}{\text{error}} \right)^{0.25}
\]
## Results
The numerical results for the test equation \( dy/dt = -2y \) show excellent agreement with the exact solution \( y(t) = e^{-2t} \). The adaptive algorithm efficiently adjusts the step size to maintain accuracy without unnecessary computation.

## Conclusion
RKF45 is a robust and practical method for numerically solving ODEs with a balance of speed and precision.