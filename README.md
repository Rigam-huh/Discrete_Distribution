# Discrete_Distribution
Discrete Distributions in R

A comprehensive guide to discrete probability distributions in R, covering mathematical foundations, implementations, and visualizations.

---

Table of Contents:
1. Key Features
2. Distributions Covered
   - Bernoulli
   - Binomial
   - Geometric
   - Poisson
   - Negative Binomial
   - Multinomial
   - Discrete Uniform
3. Key Relationships
4. Installation
5. Applications


---

Key Features:
- Mathematical derivations from first principles
- R code snippets for generating distributions
- Theoretical relationships between distributions
- Parameter conversions (e.g., Poisson to Negative Binomial)
- Interactive visualizations with histograms and PMF comparisons

---

Distributions Covered:

1. Bernoulli Distribution:
   - Single trial with success probability p
   - R Code:
     X <- ifelse(runif(n) <= p, 1, 0)

2. Binomial Distribution:
   - Sum of n independent Bernoulli trials
   - R Code:
     Y <- rowSums(matrix(runif(n * k), nrow = n) <= p)

3. Geometric Distribution:
   - Trials until first success
   - R Code:
     geom_samples <- rgeom(n, p) + 1

4. Poisson Distribution:
   - Models rare events (mean = variance = λ)
   - R Code:
     pois_samples <- rpois(n, lambda)

5. Negative Binomial Distribution:
   - Trials until r successes
   - R Code:
     negbin_samples <- rnbinom(n, size = r, prob = p)

6. Multinomial Distribution:
   - Categorical outcomes with probabilities p
   - R Code:
     multinom_samples <- rmultinom(n, size = 1, prob = p)

7. Discrete Uniform Distribution:
   - Equally likely outcomes {1,...,k}
   - R Code:
     Y <- sample(1:k, n, replace = TRUE)

---

Key Relationships:
1. Bernoulli → Binomial: Sum of n Bernoulli trials
2. Geometric → Negative Binomial: Sum of r Geometric variables
3. Negative Binomial → Poisson: Limit case when r → ∞
4. Multinomial → Discrete Uniform: Equalize category probabilities

---

Installation:
1. Clone the repository:
   git clone https://github.com/yourusername/discrete-distributions.git
2. Open Discrete_Dist.Rmd in RStudio

---

Example:
# Generate and plot Binomial samples
hist(rbinom(10000, size=10, prob=0.3), breaks=20, col="skyblue")

---

Applications:
- Statistical Modeling: Simulate call center traffic (Poisson)
- Risk Analysis: Model insurance claims (Negative Binomial)
- Machine Learning: Categorical data generation (Multinomial)

---
