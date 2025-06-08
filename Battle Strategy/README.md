# Differential Battle Models: Lanchester & Extensions

This repository contains a Python implementation of three classical combat models in a single, unified script:

1. **Lanchester Square Law** (Regular Warfare)  
2. **Lanchester Linear Law** (Irregular Warfare / Guerrilla)  
3. **Multilateral Lanchester Model** (Three‐party/Proxy/Coalition Conflict)  

All three models are computed over the same time horizon, and you can visualize them side‐by‐side as static time‐series or as an animation.  

---

##  Models Overview

### 1. Lanchester Square Law (Regular Warfare)  
- Assumes both sides deliver firepower proportional to their force size.  
- Differential equations:  
  \[
    \frac{dR}{dt} = -\,a_{RB}\,B^2, \quad
    \frac{dB}{dt} = -\,b_{RB}\,R^2
  \]  
  where \(R(t)\) = size of Red force, \(B(t)\) = size of Blue force.  
- Used for conventional massed battles (e.g., WWI/WWII fronts, set‐piece engagements).

### 2. Lanchester Linear Law (Irregular Warfare)  
- Constant‐rate attrition, independent of opposing force size.  
- Differential equations:  
  \[
    \frac{dR}{dt} = -\,a_{RB}, \quad
    \frac{dB}{dt} = -\,b_{RB}
  \]  
- Models guerrilla/insurgency style conflict where each side inflicts roughly constant losses (e.g., ambushes, skirmishes).

### 3. Multilateral Lanchester Model (Three‐Party Conflict)  
- Combines square‐law effects, linear effects, and cross‐target (“multilateral”) terms in one set of ODEs.  
- Let \(R(t)\), \(B(t)\), and \(G(t)\) be Red, Blue, and Green force sizes. Then:  
  \[
    \begin{aligned}
      \frac{dR}{dt} &= -\,a_{RB}\,B^2 \;-\; k_{RG}\,G,\\
      \frac{dB}{dt} &= -\,b_{RB}\,R^2 \;-\; a_{GL}\,G,\\
      \frac{dG}{dt} &= -\,b_{GL}\,B \;-\; k_{GR}\,R.
    \end{aligned}
  \]  
  - \(a_{RB},\,b_{RB}\) are square‐law attrition coefficients (Red vs. Blue).  
  - \(a_{GL},\,b_{GL}\) are linear attrition coefficients (Green vs. Blue).  
  - \(k_{RG},\,k_{GR}\) are cross‐effects: Green→Red and Red→Green.

---

- `battle_models_improved.py`:  
  - Computes all three models over the same time grid.  
  - Displays a static figure with three subplots (Square, Linear, Multilateral).  
  - Contains commented‐out animation code (if you choose to enable GIF/MP4 export).

---

##  Dependencies

- Python 3.6+  
- numpy  
- matplotlib  
- scipy (only if you enable advanced ODE solving or export to MP4)  
- pillow (for saving GIF animation)  
- ffmpeg (optional, for saving MP4—only needed if you uncomment the MP4 export code)

Install with:

```bash
pip install numpy matplotlib scipy pillow