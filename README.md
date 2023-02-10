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
   
## Simple Linear Regression

### 1) Build own Linear Regression Model

**Simple linear regression** is a special case when there is only one explanatory variable $X$. In this case, the relation can be represented quantitatively by:
$$
Y = \beta_0 + \beta_1X + \epsilon
$$

- $\beta_0$ and $\beta_1$ are two **unknown** constants that represent the intercept and slope.
- $\epsilon$ is called the error term.  This represents the deviation of the value from the linearity.


### 2) Evaluate the model
- The default score to measure the performance of the model is $R^2$, which is defined as $1-\frac{RSS}{TSS}$
  - $TSS$ is the total sum of squares, which measures the total variance of the output data y 
  - $TSS=\sum_{i=1}^n(y_i-\bar{y})^2$
- $R^2$ always lies between 0 and 1
  - $R^2 =1$ indicates that the regression line perfectly fits the data
  - $R^2 = 0$ indicates that the line does not fit the data at all 
- A common approach is to split the dataset into training and testing. We then train the model only use the training set and evaluate it on the test set.


### 3) Regularized Regression: Ridge and Lasso
The difference between regularized regression and normal linear regression is the **cost function**.
Since the penality term is NOT a smooth function, there is no closed form solution to Lasso model's slope coefficients. I will use **gradient** to find the best weights.

### 3-1) Lasso Regression
#### **Gradient Descent**
  - Initialized the weights of the linear model as small values, say $\beta^0$
  - for `i` in `1:n_iterations`:
    - Calculated the cost: $RSS(\beta^i) = (y-X\beta^i)^T(y-X\beta^i)$
    - Calculated the gradient: $\nabla=\frac{\partial RSS}{\partial\beta^i} = -2X^T(y-X\beta^i)$
    - Updated the value of $\beta$ by multiplying the gradient with a learning rate: $\beta^{i+1} = \beta^i - \eta\nabla$

### 3-2) Ridge Regression
- Difference between ridge and lasso is the **regularization term**
  - $Cost = (y−X\beta)^T(y−X\beta)+\lambda\beta^T\beta$
  - Ridge uses L2 norm (squared) and Lasso uses L1 norm.
- Created a general regression class with ridge and lasso to be the subclasses
