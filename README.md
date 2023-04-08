# Optimal-Market-Making

This project presents an optimal high-frequency market making strategy using the Hamilton-Jacobi-Bellman (HJB) equation.  
The project includes implementations for the following three scenarios:

1. Constant market parameter mid-price process. One is a geometric Brownian motion the other Merton's jump diffusion process

   - $\frac{dS_t}{S_t} = \mu dt + \sigma dW_t$
   - $\frac{dS_t}{S_t} = \mu dt + \sigma dW_t + \xi dN_{t}^a - \xi dN_{t}^b$

2. Stochastic volatility model(Heston model) and with jump diffusion process

   - $\begin{aligned}
      d S_t & =\mu d t+\sqrt{v_t} d B_t^1+\varepsilon^{+} d M_t^{+}-\varepsilon^{-} d M_t^{-}, \\
      d v_t & =k\left(\theta-v_t\right) d t+\sigma \sqrt{v_t} d B_t^2, \\
      d B_t^1 d B_t^2 & =\rho d t
      \end{aligned}$

3. Implied alpha and stochastic limit order book (LOB) model

   - $d S_t=\left(v+\alpha_t\right) d t+\sigma d W_t$
   - It is a measure of the adverse selection of a the market maker. The implied alpha follows the process:

   - $d \alpha_t=-\zeta \alpha_t d t+\sigma_\alpha d B_t+\epsilon^{+} d \bar{M}_t^{+}-\epsilon^{-} d \bar{M}_t^{-}+\tilde{\epsilon}^{+} d Z_t^{+}-\tilde{\epsilon}^{-} d Z_t^{-}$

   - The stochastic limit order book model is a model that is used to model the dynamics of the limit order book.  
     The model is based on the following assumptions:

   - $\left\{\begin{array}{l}
   d \kappa_t^{-}=\beta_\kappa\left(\theta_\kappa-\kappa_t^{-}\right) d t+\eta_\kappa d \bar{M}_t^{-}+\nu_\kappa d \bar{M}_t^{+}+\tilde{\eta}_\kappa d Z_t^{-}+\tilde{\nu}_\kappa d Z_t^{+}, \\
   d \kappa_t^{+}=\beta_\kappa\left(\theta_\kappa-\kappa_t^{+}\right) d t+\nu_\kappa d \bar{M}_t^{-}+\eta_\kappa d \bar{M}_t^{+}+\tilde{\nu}_\kappa d Z_t^{-}+\tilde{\eta}_\kappa d Z_t^{+},
   \end{array}\right.$

   -

The full source code is written in C++ and is not open source due to its application for real market making purposes.
