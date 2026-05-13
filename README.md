# Loglikelihood-priors-workflow
This repository is intended as a reproducible reference for prior elicitation in Bayesian regression models using a log likelihood. It contains the following files:
- data_Buerki_duration_phonemecount.csv (dataset from a published study)
- Logpriors_demo.qmd (R script that shows my personal workflow for eliciting priors for a lognormal model)


Prior elicitation is a key step in Bayesian regression modeling. In models with a Gaussian likelihood, priors can often be specified directly based on prior knowledge or interpretable expectations on the observed scale.

However, this becomes more complex when using alternative likelihoods such as the lognormal. In this case, effects are multiplicative rather than additive, and the mean depends on both location and scale parameters. As a result, priors that are intuitive on the normal scale cannot be directly transferred and must be reformulated to reflect the transformed scale and parameter interpretation.

In this repository, I provide an example workflow for eliciting priors for a lognormal model in a way that remains largely consistent with assumptions originally formulated on the normal scale. The script documents my underlying reasoning and decision-making process, including intermediate steps, to maximize transparency and practical value for others working on similar problems. The approach is based on my personal understanding of the lognormal distribution. Despite validation through prior predictive checks, it may contain errors or assumptions that do not generalize to all settings. Alternative valid strategies for prior elicitation may exist. Users are encouraged to critically evaluate and adapt the workflow to their own context.  

The workflow includes:
- Initial prior formulation on the normal scale
- Insights from published literature
- Translation of priors to the lognormal parameterization
- Validation via prior predictive checks using brms
- Final model and back-transformation of model estimates to the normal scale 

When I started working on this, I found limited accessible resources on prior elicitation for non-Gaussian likelihoods such as the lognormal. I hope that the materials shared here will be helpful for others working through similar problems and provide a useful starting point for further exploration.


The following sources were particularly helpful for me and I recommend taking a look: 

Nicenboim, B., Schad, D. J., & Vasishth, S. (2025). *Introduction to Bayesian data analysis for cognitive science*. Chapman and Hall/CRC.
(Most relevant chapters: 3.7, 4.2, 5.3, A4) 

Schad, D. J., Nicenboim, B., Bürkner, P. C., Betancourt, M., & Vasishth, S. (2023). Workflow techniques for the robust use of bayes factors. *Psychological methods*, 28(6), 1404.
