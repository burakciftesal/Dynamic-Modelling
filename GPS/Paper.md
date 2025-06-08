# 3D GPS Triangulation Using Time Difference of Arrival and Clock Bias Estimation

## Abstract

In this project, we simulate a simplified Global Positioning System (GPS) model to estimate an object’s position in three-dimensional space using three fixed beacons. By measuring time differences of arrival (TDOA) from each beacon and accounting for clock bias and measurement noise, the model optimizes for the unknown position and time offset using nonlinear least squares.

---

## 1. Introduction

Global Positioning Systems rely on satellites to send time-stamped signals. A receiver, by measuring how long these signals take to arrive from multiple satellites, can determine its location. This project recreates a simplified version of this system using Python, aiming to solve for the receiver's `(x, y, z)` coordinates and unknown clock bias.

---

## 2. Mathematical Model

### 2.1 Distance Equations

Let beacons be located at known points \( (p_i, q_i, r_i) \). The true object position is \( (x, y, z) \). The measured signal time difference (delta) from beacon \( i \) is:
\[
\delta_i = \| (x, y, z) - (p_i, q_i, r_i) \| - \| (x, y, z) - (p_{i+1}, q_{i+1}, r_{i+1}) \| + b
\]
where:
- \( \| \cdot \| \) is the Euclidean norm.
- \( b \) is the unknown **clock bias** (time offset of the receiver).

### 2.2 Residuals and Optimization

To estimate the location, we define the residual function \( F(x, y, z, b) \) for each pair of beacons:
\[
r_i = \left( \| (x, y, z) - P_i \| - \| (x, y, z) - P_{i+1} \| - \delta_i \right)
\]
We minimize the sum of squared residuals:
\[
\min_{x, y, z, b} \sum_{i=1}^n r_i^2
\]
using SciPy’s `least_squares` optimizer.

---

## 3. Implementation

- **Language:** Python 3
- **Libraries:** NumPy, SciPy, Matplotlib
- **Simulation Setup:**
  - 3 beacons placed in 3D space
  - True object location defined
  - TDOA calculated with Gaussian noise
  - Optimization initialized far from the true position

---

## 4. Results

The system correctly converges toward the true object position even with added noise and clock bias. Visualization includes:
- Gray lines showing optimization path
- Green dot for true location
- Red dot for estimated location
---

## 5. Extensions
Future work may include:
- Real-time Kalman filtering for moving targets
- 4+ beacons to resolve ambiguity and improve accuracy
- Incorporation of satellite orbits and signal propagation delay
---

## 6. Conclusion

This project demonstrates how GPS localization can be modeled as a nonlinear optimization problem. Despite simplifications, it reflects key aspects of satellite positioning systems and serves as a platform for further exploration in localization theory and simulation.