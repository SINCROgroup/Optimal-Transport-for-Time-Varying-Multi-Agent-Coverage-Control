# Optimal Transport for Time-Varying Multi-Agent Coverage Control

This repository contains the supplementary materials and demonstration videos associated with the paper:  

**[1]** Italo Napolitano, Mario di Bernardo, *"Semi-discrete Optimal Transport for Time-Varying Multi-Agent Coverage Control,"* arXiv:2601.21753, 2026.  

# Repository structure  
- **`MOVIE_2D.mp4`**: Simulation from Section 5 (Fig. 1 in [1]). Eight agents (black dots) track the time-varying target 2D distribution (colormap) which (1) has mean varying linearly and variance varing sinusoidally time; (2) splits into a bimodal distribution with constant variance and mean varying linearly in time.
- **`Wasserstein_2D.pdf`**: Wasserstein error over time related to the experiment `MOVIE_2D.mp4` (simulation from Section 5), comparing TVOT-C (black solid lines); TVOT-D$_4$ (dashed red lines); TVOT-D$_1$ (dotted green lines); and TVOT-G (solid blue lines).
- **`MOVIE_1Dsinusoidal.mp4`**: Simulation from Section 5.1 (Fig. 2b in [1]). Five agents (black dots) track the time-varying target 1D monomodal distribution (red line) whose mean and variance vary sinusoidally in time.
- **`MOVIE_1Dbimodal.mp4`**: Additional simulation. Five agents (black dots) track the time-varying target 1D bimodal distribution (red line) whose mean varies linearly in time.
- **`Wasserstein_1Dbimodal.pdf`**: Wasserstein error over time related to the experiment `MOVIE_1Dbimodal.mp4` (simulation from Section 5), comparing TVOT-C (black solid lines); TVOT-D$_1$ (dashed red lines); TVOT-G (solid blue lines); OTCC \cite{inoue2020optimal} (solid green lines); TVV-C \cite{lee2015multirobot} (dashed brown lines).
- **`PositionError_1Dbimodal.pdf`**: Position error norm over time related to the experiment `MOVIE_1Dbimodal.mp4` (simulation from Section 5), comparing TVOT-C (black solid lines); TVOT-D$_1$ (dashed red lines); TVOT-G (solid blue lines); OTCC \cite{inoue2020optimal} (solid green lines); TVV-C \cite{lee2015multirobot} (dashed brown lines).
- **`MassError_1Dbimodal.pdf`**: Mass error norm over time related to the experiment `MOVIE_1Dbimodal.mp4` (simulation from Section 5), comparing TVOT-C (black solid lines); TVOT-D$_1$ (dashed red lines); TVOT-G (solid blue lines); OTCC \cite{inoue2020optimal} (solid green lines); TVV-C \cite{lee2015multirobot} (dashed brown lines).

# Additional simulation
Validation in a one-dimensinal domanin, where $5$ agents track a bimodal Gaussian distribution $0.5 \mathcal{N}(m_1(t), \sigma) + 0.5 \mathcal{N}(m_2(t), \sigma)$ with $\dot m_{i} (t)  = v_{m,i}$. The agents split into two groups near the peaks, accurately reproducing the target density.

# Quantitative analysis
*Performance metrics where $\mathcal{W}_2:=\limsup_{t \to \infty} \mathcal{W}_2(\mu_t, \bar \mu_t)$; $e_p:=\limsup_{t \to \infty} \lVert e_p \rVert$, and $e_p:=\limsup_{t \to \infty} \lVert e_p \rVert$.*

*2D Experiment*
| Method | $\mathcal{W}_2$ | $e_p$ |  $e_a$ |
|---|---:|---:|---:|
| TVOT-C | 3.56 | 1e-4 | 5e-7 |
| TVOT-G | 3.61 | 0.65 | 0.03 |
| TVOT-D$_1$ | 3.61 | 0.33 | 0.04 |
| TVOT-D$_4$ | 3.61 | 0.29 | 0.03 |

*1D Experiment with sinusoidally varying mean and variance*
| Method | $\mathcal{W}_2$ | $e_p$ |  $e_a$ |
|---|---:|---:|---:|
| TVOT-C | 1.25 | 8e-4 | 2e-4 |
| TVOT-G | 1.28 | 0.01 | 0.05 |
| TVOT-D$_1$ | 1.35 | 0.33 | 0.1 |
| TVV-C | 1.60 | 6e-3 | 0.18 |
| OTCC | 1.86 | 1.21 | 0.16 |

# Simulations parameters

*Parameters used in the 2D experiment.*
| Parameter | Value | Parameter | Value |
|---|---|---|---|
| $\Omega$ | $[0,50]^2$ | $\lambda_1$ | 9 |
| $\Delta t$ | 0.01 | $\lambda_2$ | 10 |
| $\Delta x$ | 0.5 | $\boldsymbol{m}_0$ | $[10, 10]$ |
| $K_x$ | 10 | $\boldsymbol{\Sigma}$ | $\mathrm{diag}(15, 15)$ |
| $K_{\phi}$ | 10 | $\dot{\boldsymbol{m}}$ | $[10, 5]$ |
| $\boldsymbol{z}_0(0)$ | $\mathbf{0}_N$ | $\boldsymbol{z}_0(0)$ | $\mathbf{0}_N$ |


*Parameters used in the 1D experiment.*
| Parameter | Sinusoidal | Bimodal |
|---|---:|---:|
| $\Omega$ | $[0,50]$ | $[0,50]$ |
| $K_x$ | 10 | 1 |
| $K_{\phi}$ | 10 | 1 |
| $\Delta t$ |  0.01 | 0.01 |
| $\Delta x$ | 0.01 | 0.01 |
| $m_0$ | 20 | 10, 20 |
| $\sigma_0$ | 3 | 2, 2 |
| $\dot{m}$ |-5 | 1, 1 |
| $\dot{\sigma}$ |1 | 0, 0 |
