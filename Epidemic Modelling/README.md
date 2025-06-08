 SIQRV Epidemic Model

A Python implementation of an S–I–Q–R–V compartmental model (Susceptible, Infectious, Quarantined, Recovered, Vaccinated) that demonstrates how isolation and vaccination shape an outbreak.

## Model Equations

\[
\begin{aligned}
\frac{dS}{dt} &= -\beta\,\frac{S\,I}{N} \;-\; \nu\,S,\\
\frac{dI}{dt} &= \beta\,\frac{S\,I}{N} \;-\; (\gamma + \delta)\,I,\\
\frac{dQ}{dt} &= \delta\,I \;-\; \epsilon\,Q,\\
\frac{dR}{dt} &= \gamma\,I \;+\; \epsilon\,Q,\\
\frac{dV}{dt} &= \nu\,S,
\end{aligned}
\]
where  
• \(\beta\) = infection rate,  
• \(\gamma\) = recovery rate (I→R),  
• \(\delta\) = isolation rate (I→Q),  
• \(\epsilon\) = recovery rate (Q→R),  
• \(\nu\) = vaccination rate (S→V),  
and \(N = S+I+Q+R+V\) is constant.

## Requirements

- Python 3.6+  
- numpy, scipy, matplotlib

```bash
pip install numpy scipy matplotlib