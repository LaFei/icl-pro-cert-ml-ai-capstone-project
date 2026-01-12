MODEL CARD

Intended use

Primary tasks: propose one new query point per function each round to improve best observed outputs; adapt step size/direction based on recent trends (plateau vs improving vs unstable)
Target users: capstone learners, reviewers/facilitators assessing reasoning and reproducibility, practitioners exploring lightweight optimisation heuristics under limited evaluations
Use case: iterative optimisation when only a small number of expensive evaluations are available; producing auditable decision rationales for each query
Limitations: not guaranteed to find global optima; performance is sensitive to early sampling (path dependence); relies on assumptions of local smoothness and can fail on rugged/discontinuous objectives; should be treated as a decision aid rather than an optimal solver

Training data

Size: ~Weeks 1–10 × 8 functions ≈ ~80 evaluations (plus any initial seed points)
Sources: portal-returned function evaluations from submitted queries (black-box objective functions provided by the course platform)
Features: per-function input vectors in 0,1 with fixed dimensionality (F1–F2: 2D; F3: 3D; F4–F5: 4D; F6: 5D; F7: 6D; F8: 8D) and a scalar output per query

Inputs and outputs

Input: numeric vector formatted as six decimals; each value in 0,1; dimension depends on the function
Output: scalar real-valued evaluation returned by the portal (used as the optimisation performance signal)

Ethical considerations

Bias risks: no personal/demographic data are involved; the main risks are methodological bias, sampling bias toward local regions, path dependence, and over-interpreting limited evidence.
Transparency: query history is logged with week index, inputs and outputs; decision notes capture why each query was chosen
Recommendations: document assumptions and step-size rules; avoid over-claiming generality or global optimality; version the dataset weekly; provide reproducibility notebooks and a changelog for corrections

Distribution

Model card and code available in open repositories for scrutiny and improvement
