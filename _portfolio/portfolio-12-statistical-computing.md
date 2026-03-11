---
title: "Statistical Computing: Simulation, Monte Carlo, MCMC, Hypothesis Testing, Optimization, EM Algorithm, and Gaussian Processes"
excerpt: "Random variate generation, Monte Carlo integration, MCMC sampling, bootstrap and permutation tests, power analysis, Newton-Raphson optimization, EM algorithm for mixtures, Gaussian process regression, and Bayesian optimization.<br/>"
collection: portfolio
---

<div style="background: linear-gradient(135deg, #3b0764 0%, #7c3aed 50%, #a78bfa 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #ddd6fe; margin-top: 0; font-size: 1.6em;">The Engine Room of Statistics — Built from Scratch</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    Implementing the computational backbone of modern statistics: <strong>Monte Carlo</strong>, <strong>MCMC</strong>, <strong>EM algorithm</strong>, <strong>Newton-Raphson</strong>, <strong>Gaussian processes</strong>, and <strong>Bayesian optimization</strong> — all coded from the ground up across 7 reports.
  </p>
</div>

## Methods — A Computational Statistics Roadmap

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">Simulation & Monte Carlo</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Inverse CDF, acceptance-rejection, antithetic variates, importance sampling, control variates</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">Reports 1-2</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">MCMC Sampling</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Metropolis-Hastings, Gibbs sampler, convergence diagnostics, trace plots, ESS</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">Reports 1-2</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">Bootstrap & Testing</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Jarque-Bera normality test, power analysis, bootstrap, permutation tests</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">Report 3</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">Newton-Raphson MLE</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Analytical gradient & Hessian, line search, heteroscedastic models</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">Report 4</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">EM Algorithm</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Gaussian mixture models, E-step/M-step, monotone log-likelihood convergence</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">Report 5</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">GP & Bayesian Optimization</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Matern covariance MLE, kriging, Expected Improvement acquisition</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">Report 6 & Midterm</span>
  </div>
</div>

## Key Results

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #a78bfa; margin: 0;">Algorithms Implemented from Scratch</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">Every method coded, validated, and analyzed — not just called from a library</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">Quadratic</span><br><span style="color: #aaa;">Newton-Raphson convergence</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">EM</span><br><span style="color: #aaa;">Recovered true parameters</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">GP</span><br><span style="color: #aaa;">Calibrated uncertainty</span></div>
  </div>
</div>

- Importance sampling with well-chosen proposals achieved **significant variance reduction** over crude Monte Carlo.
- Jarque-Bera test showed high power against heavy-tailed alternatives but low power against symmetric non-normals.
- EM algorithm recovered true mixture parameters with monotone log-likelihood convergence.
- Newton-Raphson achieved **quadratic convergence**, matching R's `optim` output.
- GP regression with Matern covariance provided accurate spatial predictions with calibrated uncertainty bands.

<div style="margin-top: 25px;">
  <a href="/files/SC_HW1_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW1</a>
  <a href="/files/SC_HW2_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW2</a>
  <a href="/files/SC_HW3_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW3</a>
  <a href="/files/SC_HW4_Optimization.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW4</a>
  <a href="/files/SC_HW5_EM_Algorithm.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW5</a>
  <a href="/files/SC_HW6_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW6</a>
  <a href="/files/SC_Midterm_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">Midterm</a>
</div>
