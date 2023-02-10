# Regression Model on predicting Wine Quality

## Data Explanation
**Wine quality inspection with input vairables below**

- Input variables (based on physicochemical tests):
   - fixed acidity
   - volatile acidity
   - citric acid
   - residual sugar
   - chlorides
   - free sulfur dioxide
   - total sulfur dioxide
   - density
   - pH
   - sulphates
   - alcohol
- Output variable (based on sensory data): 
   "- quality (score between 0 and 10)
   

**Simple linear regression** is a special case when there is only one explanatory variable $X$. In this case, the relation can be represented quantitatively by:
$$
Y = \beta_0 + \beta_1X + \epsilon
$$

- $\beta_0$ and $\beta_1$ are two **unknown** constants that represent the intercept and slope.
- $\epsilon$ is called the error term.  This represents the deviation of the value from the linearity.
