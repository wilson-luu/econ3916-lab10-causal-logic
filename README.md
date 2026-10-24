# Correlation & Causality: Confounders, Colliders and the Limits of Controls

**Objective:** This project demonstrates through simulation and directed acyclic graphs (DAGs) how confounding, selection bias, and M-bias distort causal estimates, and shows that blindly adding controls can introduce bias rather than remove it.

**Methodology:**
* Simulated three worlds (true causation, pure confounding and pure selection) whose correlations all come out near 0.65, although the true effects are 2.0, 0.0 and 0.0
* Drew a confounder, a collider and a mediator as directed graphs with networkx
* Showed that controlling for a confounder recovers the true effect, while controlling for a collider creates a large, highly significant association between two independent variables
* Built an M-bias structure in which a control measured BEFORE treatment still biases the estimate
* Wrote a small function, coef_on_d(), that returns the coefficient on the treatment for any list of controls, and used it to show that also controlling for one of the hidden causes closes the path again
* Reproduced the LaLonde (1986) contrast: the randomised experiment against a comparison group from the CPS, then measured how much of the gap covariate adjustment closes

**Key Findings:**
Correlations 0.654, 0.664 and 0.632; the collider control gave -0.592 where the truth is 0; M-bias gave -0.191, and 0.000 once I also controlled for u1; LaLonde: experimental $1,794, naive CPS $-8,498, with controls $699 (89% of the gap closed).
