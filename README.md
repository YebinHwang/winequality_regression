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
