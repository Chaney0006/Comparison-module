# Comparison-module
| Comparison module | Comparison item | Model / Design / Scenario I | Model / Design / Scenario II |
|---|---|---|---|
| **Target model** | Model type | Point target model | Extended target model |
|  | Target response matrix | $H=\alpha a(\theta)a^T(\theta)$ | General target response matrix $H$ |
|  | Estimated parameter | Target angle $\theta$ | Target response matrix $H$ |
|  | Received signal | $y(t)=G_r\Phi^T H\Phi G_t x(t)+n(t)$ | $y(t)=G_r\Phi^T H\Phi G_t x(t)+n(t)$ |
|  | CRB metric | $\mathrm{CRB}(\theta)$ |<img width="264" height="41" alt="image" src="https://github.com/user-attachments/assets/05b1a3ed-a667-4875-ad95-fd5deac40212" /> |
|  | CRB-related parameters | $R_x,v,R_1,R_2,\sigma_R^2,T,\alpha^2,\theta,d_{\mathrm{IRS}},\lambda_R$ | $R_x,G_t,G_r,\sigma_R^2,T$ |
|  | Estimability condition | rank(Gt)>1 or rank(Gr)>1| rank(Gt​)=rank(Gr​)=N |
|  | Optimization method | Alternating optimization (AO) | SVD and power allocation |
| **Sensing-constrained design** | Design type | SNR-constrained design | CRB-constrained design |
|  | Sensing task | Target detection | Target DoA estimation |
|  | Performance metric | Radar SNR | Cramér–Rao Bound (CRB) |
|  | Estimated parameter | Whether the target exists | Target angles $\boldsymbol{\theta}=[\theta_1,\theta_2]^T$ |
|  | Received radar signal | $Y_r=\alpha_tH_t(\phi)WS+N_r$ | $Y_r=\alpha_tH_t(\phi)WS+N_r$ |
|  | Optimization objective | Maximize the achievable communication sum-rate | Maximize the achievable communication sum-rate |
|  | Sensing constraint | $\mathrm{SNR}_t\geq\Gamma_t$ |<img width="155" height="26" alt="image" src="https://github.com/user-attachments/assets/554b9653-452e-410e-b345-3fedfd502969" /> |
|  | Other constraints | $\lVert W\rVert_F^2\leq P_t,\quad\lvert\phi_n\rvert=1$ | $\lVert W\rVert_F^2\leq P_t,\quad\lvert\phi_n\rvert=1$ |
|  | Optimized variables | Beamforming $W$, receive filter $u$, and RIS coefficients $\phi$ | Beamforming $W$ and RIS coefficients $\phi$ |
|  | Main methods | FP + MM + ADMM | FP + MM + BCD + penalty dual decomposition |
|  | Effect of more RIS elements | Improves target detection and communication sum-rate | Provides a larger gain for DoA estimation |
|  | Simulation result | Sum-rate increases by approximately 40% | Sum-rate increases by approximately 76% |
|  | Residual self-interference | Causes performance loss | Causes more significant performance loss |
| **Multi-target sensing** | Scenario | Scenario I | Scenario II |
|  | Prior target knowledge | No prior target knowledge | Prior target knowledge is available |
|  | Practical stage | Target detection | Target tracking |
|  | Sensing objective | Estimate the complete multi-target response matrix | Estimate the angles and complex coefficients of multiple targets |
|  | Estimated parameter | $G=A_r^cBA_t^H$ | $\boldsymbol{\xi}=[\boldsymbol{\theta}^T,\boldsymbol{\beta}_R^T,\boldsymbol{\beta}_I^T]^T$ |
|  | Received echo signal | $Y=A_r^cBA_t^HX+Z$ | $Y=A_r^cBA_t^HX+Z$ |
|  | CRB metric | <img width="161" height="43" alt="image" src="https://github.com/user-attachments/assets/24e5bc2f-9332-4e0e-b880-1960907262ad" /> | <img width="184" height="32" alt="image" src="https://github.com/user-attachments/assets/ee91aaf4-142d-4255-8739-8c7cff886b3b" />|
|  | Optimization objective | Minimize $\mathrm{CRB}_1(S_x)$ | Minimize $\mathrm{CRB}_2(S_x)$ |
|  | Rate constraint | $R(S_x)\geq\bar{R}$ | $R(S_x)\geq\bar{R}$ |
|  | Power constraint | tr(Sx​)≤P | tr(Sx​)≤P |
|  |Original problem|<img width="226" height="74" alt="image" src="https://github.com/user-attachments/assets/70f46e3c-f404-46c7-908c-28052df1eb71" /> |<img width="203" height="62" alt="image" src="https://github.com/user-attachments/assets/24691ac7-3411-46dc-beaa-b71c746eb098" />|
|  | Optimized variable | Transmit covariance matrix $S_x$ | Transmit covariance matrix $S_x$ |
|  | Solution method | Lagrange duality and convex optimization | Semidefinite programming (SDP) |
|  | Beamforming algorithm | SCA | SCA |
