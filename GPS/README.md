# 3D GPS Triangulation with Clock Bias and Noisy Measurements

This project implements a 3D GPS localization model in Python that estimates an object's position in space based on known beacon locations and time difference of arrival (TDOA) measurements. It simulates noisy GPS data and includes clock bias correction using numerical optimization techniques.

## 📌 Features

- Triangulation using 3 beacons in 3D space.
- Optimization of `(x, y, z)` coordinates and clock bias.
- Noisy delta time simulation to reflect real GPS uncertainty.
- Visualization of:
  - Beacon positions
  - True and estimated object positions
  - Optimization trajectory
- Extendable architecture for additional beacons and accuracy experiments.

## 📐 Problem Statement

Given:
- Known beacon positions in 3D.
- Simulated time differences of arrival (TDOA) to the beacons.
- Optional noise on measurements and unknown clock bias.

The goal is to:
- Reconstruct the object's position by minimizing the residuals between measured and estimated TDOA values using nonlinear least squares.

## ⚙️ Technologies

- **Python 3.8+**
- `numpy`
- `scipy.optimize`
- `matplotlib` (for 3D visualization)

## 🚀 How to Run

```bash
pip install numpy scipy matplotlib
python gps_solver.py
