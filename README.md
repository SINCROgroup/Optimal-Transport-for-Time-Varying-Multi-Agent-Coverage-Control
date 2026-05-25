# Optimal Transport for Time-Varying Multi-Agent Coverage Control

This repository contains the supplementary materials and demonstration videos associated with the paper:  

**[1]** Italo Napolitano, Mario di Bernardo, *"Semidiscrete Optimal Transport for Time-Varying Multi-Agent Coverage Control,"* 2026.  

# Repository structure  
- **`MOVIE1.mp4`**: Simulation from Section 4.2 (Fig. 1 in [1]). Eight agents (black dots) track the time-varying target 2D distribution (colormap) which (1) has mean varying linearly and variance varing sinusoidally time; (2) splits into a bimodal distribution with constant variance and mean varying linearly in time.
- **`MOVIE1_Wasserstein.pdf`**: Wasserstein error over time related to the experiment `bimodal2D.mp4` (simulation from Section 4.2).
- **`MOVIE2.mp4`**: Additional simulation. Seven agents (black dots) track the time-varying target 2D monomodal distribution (colormap) whose mean varies linearly in time.
- **`MOVIE2_Wasserstein.pdf`**: Wasserstein error over time related to the experiment `monomodal2D.mp4` (Additional 2D simulation).
- **`MOVIE3.mp4`**: Simulation from Section 5.1 (Fig. 2a in [1]). Five agents (black dots) track the time-varying target 1D monomodal distribution (red line) whose mean varies linearly in time.
- **`MOVIE4.mp4`**: Simulation from Section 5.1 (Fig. 2b in [1]). Five agents (black dots) track the time-varying target 1D monomodal distribution (red line) whose mean and variance vary sinusoidally in time.
- **`MOVIE5.mp4`**: Additional simulation. Five agents (black dots) track the time-varying target 1D bimodal distribution (red line) whose mean varies linearly in time.

# Additional simulations
## Sec. 4.2 additional simulation
Validation in a two-dimensional domain where $7$ agents track a Gaussian distribution $\mathcal{N}(\boldsymbol{m}(t), \boldsymbol{\Sigma})$ with linearly moving mean $\dot{\boldsymbol{m}}(t) = [v_{m,x}, v_{m,y}]$. The agents, initialized at random positions, rapidly reposition to cover the target and continue tracking it as the distribution moves across the domain. The related video can be found in  `MOVIE2.mp4`.

## Sec. 6 additional simulation
Validation in a one-dimensinal domani, where $5$ agents track a bimodal Gaussian distribution $0.5 \mathcal{N}(m_1(t), \sigma) + 0.5 \mathcal{N}(m_2(t), \sigma)$ with $\dot m_{i} (t)  = v_{m,i}$. The agents split into two groups near the peaks, accurately reproducing the target density. The related video can be found in  `MOVIE5.mp4`.

# Performance metrics
*Performance metrics for TV-OT, TV-V, and OTCC across the three scenarios in Sec.6, where scenario 3 refers to the additional simulation presented in this repository.*
| Scenario | Method | $\mathcal{W}_2$ | $D_{KL}$ |
|---|---|---:|---:|
| 1 | TV-OT | 0.2003 | 0.0250 |
| 1 | TV-V  | 0.8052 | 0.1507 |
| 1 | OTCC  | 5.1054 | 0.7122 |
| 2 | TV-OT | 0.6933 | 0.0697 |
| 2 | TV-V  | 1.1233 | 0.1316 |
| 2 | OTCC  | 5.3996 | 0.5307 |
| 3 | TV-OT | 1.0289 | 0.3025 |
| 3 | TV-V  | 1.1464 | 0.3096 |
| 3 | OTCC  | 1.5604 | 0.3239 |


# Simulations parameters

*Parameters used in the experiment for Sec.4.2.*
| Parameter | Value | Parameter | Value |
|---|---|---|---|
| $\Omega$ | $[0,50]^2$ | $\lambda_1$ | 9 |
| $\Delta t$ | 0.01 | $\lambda_2$ | 10 |
| $\Delta x$ | 0.5 | $\boldsymbol{m}_0$ | $[10, 10]$ |
| $K_x$ | 20 | $\boldsymbol{\Sigma}$ | $\mathrm{diag}(15, 15)$ |
| $K_{\phi}$ | 10 | $\dot{\boldsymbol{m}}$ | $[10, 5]$ |
| $\boldsymbol{z}_0(0)$ | $\mathbf{0}_N$ | $\boldsymbol{z}_0(0)$ | $\mathbf{0}_N$ |


*Parameters used in the experiment for Sec.5.2 and 6, where scenario 3 refers to the additional simulation presented in this repository.*
| Parameter | Exp 1 | Exp 2 | Exp 3 |
|---|---:|---:|---:|
| $\Omega$ | $[0,60]$ | $[0,50]$ | $[0,50]$ |
| $K_x$ | 2 | 5 | 5 |
| $K_{\phi}$ | 1 | 2.5 | 1 |
| $\Delta t$ | 0.01 | 0.01 | 0.01 |
| $\Delta x$ | 0.012 | 0.01 | 0.01 |
| $m_0$ | 10 | 20 | 10, 20 |
| $\sigma_0$ | 2.5 | 3 | 2, 2 |
| $\dot{m}$ | 2 | -5 | 1, 1 |
| $\dot{\sigma}$ | 0 | 1 | 0, 0 |
