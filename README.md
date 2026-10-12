# Data repository (arXiv:2607.09216)
Data repository for the paper
"Hunting for new physics in $B$ meson $b\to u$ transitions: A fresh look with Belle II data",
P. Colangelo, F. De Fazio, M.L. Di Cuia, and D. Milillo, [arXiv:2607.09216v2](https://arxiv.org/abs/2607.09216).

## Posterior samples

MCMC posterior samples of the global fit of $B^-\to\mu^-\bar\nu_\mu$, $\bar B^0\to\pi^+\mu^-\bar\nu_\mu$ and $B^-\to\rho^0\mu^-\bar\nu_\mu$ one file per benchmark value of $|V_{ub}|$ (fixed in the fit).

Files:
- [`global_samples_Vubmin.txt`](samples/global_samples_Vubmin.txt): $|V_{ub}| = 3.51\times10^{-3}$
- [`global_samples_Vubmid.txt`](samples/global_samples_Vubmid.txt): $|V_{ub}| = 3.85\times10^{-3}$
- [`global_samples_Vubmax.txt`](samples/global_samples_Vubmax.txt): $|V_{ub}| = 4.19\times10^{-3}$

Columns: `chain, step, Re_eps1, Im_eps1, Re_eps2, Im_eps2, Re_epsS, Im_epsS,
Re_epsP, Im_epsP, Re_epsT, Im_epsT, logL`, where `logL` is the log-likelihood (up to an additive constant).

Setup:
- 4 independent chains of 500 000 steps each, started from random points within prior ranges.
- Metropolis algorithm with uniform proposal; widths 0.3 for all couplings,
  except Re($\epsilon_P^\mu$) and Im($\epsilon_P^\mu$), for which the width is 0.01.
- Rejected steps are repeated in the chain, so the samples are properly weighted.
- No burn-in removed. Files are thinned uniformly, keeping one step every 100.
- Priors: uniform in $[-1,+1]$ for Re and Im of each coupling; for $\epsilon_P^\mu$ the rectangle $[-0.06,+0.03]\times[-0.04,+0.04]$. The leptonic bound is imposed only through this choice, not on individual samples.
