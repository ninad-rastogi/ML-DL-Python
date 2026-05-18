**Complete OLS Regression Results Explanation**

This output is from an **OLS (Ordinary Least Squares) Linear Regression** model using the `statsmodels` library.

The model predicts:

- **Dependent Variable (Target):** `price`
- **Independent Variable (Feature):** `room_num`

---

**Regression Equation**

General regression equation:

$$
Y = \beta_0 + \beta_1X
$$

For this model:

$$
price = -34.6592 + 9.0997(room\_num)
$$

Where:

- $\beta_0$ = intercept (constant)
- $\beta_1$ = slope coefficient

---

1. **Dependent Variable**

**Dep. Variable: `price`**

This is the target variable the model tries to predict.

The model learns how `room_num` affects house price.

---

2. **Model Type**

**Model: `OLS`**

OLS = Ordinary Least Squares.

OLS finds the best-fit regression line by minimizing the squared residual errors.

Residual/Error:

$$
Residual = Actual - Predicted
$$

OLS minimizes:

$$
\sum (y_i - \hat{y}_i)^2
$$

Where:

- $y_i$ = actual value
- $\hat{y}_i$ = predicted value

Errors are squared because:

- negative errors become positive
- large errors are penalized more strongly
- easier mathematical optimization

---

3. **Method**

**Method: Least Squares**

The regression line is selected such that the total squared error becomes minimum.

---

4. **Number of Observations**

**No. Observations: `506`**

The dataset contains 506 rows.

So the model was trained using 506 samples.

---

5. **Degrees of Freedom**

---

**Df Model: `1`**

This means there is 1 predictor variable:

```python
room_num
```

---

**Df Residuals: `504`**

Formula:

$$
Df_{Residual} = n - p - 1
$$

Where:

- $n$ = number of observations
- $p$ = number of predictors

Calculation:

$$
506 - 1 - 1 = 504
$$

Residual degrees of freedom represent remaining independent information after fitting the model.

---

6. **R-squared**

**R-squared = `0.485`**

R² measures how much variation in the target variable is explained by the model.

Formula:

$$
R^2 = 1 - \frac{SS_{res}}{SS_{tot}}
$$

Where:

- $SS_{res}$ = residual sum of squares
- $SS_{tot}$ = total sum of squares

Interpretation:

- 0 → model explains nothing
- 1 → perfect prediction

Here:

$$
R^2 = 0.485
$$

Meaning:

- 48.5% of variation in house prices is explained by `room_num`
- 51.5% variation remains unexplained

This is decent for a single-variable regression.

---

7. **Adjusted R-squared**

**Adj. R-squared = `0.484`**

Adjusted R² penalizes unnecessary variables.

Formula:

$$
Adjusted\ R^2 = 1-(1-R^2)\frac{n-1}{n-p-1}
$$

Normal R² always increases when new variables are added, even useless ones.

Adjusted R² increases only when predictors genuinely improve the model.

Since there is only one predictor:

- R² = 0.485
- Adjusted R² = 0.484

Both are almost identical.

---

8. **F-statistic**

**F-statistic = `474.3`**

Tests whether the overall regression model is statistically useful.

**Hypotheses:**

- **Null Hypothesis ($H_0$)**

$$
\beta_1 = 0
$$

The predictor has no effect.

- **Alternative Hypothesis ($H_1$)**

$$
\beta_1 \neq 0
$$

The predictor affects the target.

Large F-statistic means:

- the model explains significant variation
- regression relationship is strong

  474.3 is extremely high.

---

9. **Prob(F-statistic)**

**Prob(F-statistic) = `1.31e-74`**

This is the p-value for the overall regression model.

Very tiny value:

$$
1.31 \times 10^{-74}
$$

Interpretation:

- model is highly significant
- reject null hypothesis
- `room_num` significantly affects `price`

Rule:

- p-value < 0.05 → statistically significant

---

10. **Coefficient Table**

| Variable | coef     | std err | t       | P>\|t\| |
| -------- | -------- | ------- | ------- | ------- |
| const    | -34.6592 | 2.642   | -13.118 | 0.000   |
| room_num | 9.0997   | 0.418   | 21.779  | 0.000   |

---

11. **Intercept (const)**

**coef = `-34.6592`**

This is the intercept.

Meaning:
When `room_num = 0`:

$$
price = -34.6592
$$

Practically unrealistic because houses cannot have zero rooms.

Intercept mainly helps position the regression line mathematically.

---

12. **Standard Error of Intercept**

**std err = `2.642`**

This measures uncertainty in the intercept estimate.

Interpretation:

- smaller standard error → more reliable estimate
- larger standard error → less certainty

The intercept estimate may vary approximately by ±2.642 units.

---

13. **t-statistic for Intercept**

**t = `-13.118`**

Formula:

$$
t = \frac{Coefficient}{Standard\ Error}
$$

Calculation:

$$
t = \frac{-34.6592}{2.642} \approx -13.118
$$

Large absolute t-value means the intercept is statistically different from zero.

---

14. **P-value for Intercept**

**P>|t| = `0.000`**

Very small p-value indicates:

- intercept is statistically significant
- intercept is unlikely to be zero

---

15. \*\*Confidence Interval for Intercept

**95% CI = `[-39.850, -29.468]`**

Meaning:
With 95% confidence, the true intercept lies between:

- -39.850
- -29.468

Since 0 is not inside the interval:

- intercept is statistically significant

---

16. **Coefficient of `room_num`**

**coef = `9.0997`**

This is the slope coefficient.

Meaning:
For every increase of 1 room:

$$
price \ increases \ by \ approximately \ 9.1 \ units
$$

This is the main learning from the model.

---

17. **Standard Error of `room_num`**

**std err = `0.418`**

Measures uncertainty in the slope estimate.

Smaller standard error means:

- coefficient estimate is stable
- model is confident about the relationship

Since 0.418 is relatively small compared to 9.0997:

- the coefficient estimate is reliable

---

18. **t-statistic for `room_num`**

**t = `21.779`**

Formula:

$$
t = \frac{Coefficient}{Standard\ Error}
$$

Calculation:

$$
t = \frac{9.0997}{0.418} \approx 21.779
$$

Very large t-value means:

- `room_num` strongly contributes to prediction
- relationship is statistically significant

---

19. **P-value for `room_num`**

**P>|t| = `0.000`**

Hypotheses:

- **Null Hypothesis**

$$
\beta_1 = 0
$$

- **Alternative Hypothesis**

$$
\beta_1 \neq 0
$$

Very small p-value means:

- reject null hypothesis
- `room_num` significantly affects house price

---

20. **Confidence Interval for `room_num`**

**95% CI = `[8.279, 9.921]`**

Meaning:
With 95% confidence, the true slope lies between:

- 8.279
- 9.921

Since 0 is not inside the interval:

- the predictor is statistically significant

---

21. **Log-Likelihood**

**Log-Likelihood = `-1671.6`**

Measures how likely observed data is under the model.

Higher values (less negative) are better.

Mostly useful for comparing models.

---

22. **AIC**

**AIC = `3347`**

AIC = Akaike Information Criterion.

Used for model comparison.

Formula includes:

- goodness of fit
- penalty for complexity

Lower AIC is better.

---

23. **BIC**

**BIC = `3356`**

BIC = Bayesian Information Criterion.

Similar to AIC but penalizes model complexity more strongly.

Lower BIC is better.

---

24. **Omnibus Test**

**Omnibus = `103.753`**

Tests whether residuals are normally distributed.

Large value suggests:

- residuals are not normal

---

25. **Prob(Omnibus)**

**Prob(Omnibus) = `0.000`**

Very small p-value means:

- residuals are not normally distributed
- regression assumption is violated

---

26. **Jarque-Bera Test**

**Jarque-Bera (JB) = `633.429`**

Another normality test.

High value indicates:

- skewness
- heavy tails
- outliers

Residuals are not normally distributed.

---

27. **Prob(JB)**

**Prob(JB) = `2.84e-138`**

Extremely small p-value confirms:

- residuals are not normal

---

28. **Skew**

**Skew = `0.729`**

Measures asymmetry of residual distribution.

Interpretation:

- 0 → symmetric
- positive → right-skewed
- negative → left-skewed

Residuals are positively skewed.

---

29. **Kurtosis**

**Kurtosis = `8.284`**

Measures heaviness of tails.

Normal distribution kurtosis ≈ 3.

Since:

$$
8.284 > 3
$$

Residuals contain:

- heavy tails
- potential outliers

---

30. **Durbin-Watson Statistic**

**Durbin-Watson = `0.681`**

Tests autocorrelation in residuals.

Range:

- 2 → no autocorrelation
- <2 → positive autocorrelation
- \>2 → negative autocorrelation

Since:

$$
0.681
$$

There is strong positive autocorrelation.

---

31. **Condition Number**

**Cond. No. = `58.4`**

Measures numerical stability and multicollinearity.

Interpretation:

- <30 → good
- 30 to 100 → moderate concern
- \>100 → serious concern

  58.4 indicates moderate numerical instability but not severe.

---

**Final Overall Interpretation**

The regression analysis shows:

- `room_num` strongly affects house price
- relationship is statistically significant
- the predictor has a strong positive coefficient
- the model explains 48.5% of variation in house prices

However:

- residuals are not normally distributed
- outliers may exist
- autocorrelation exists
- one predictor alone cannot fully explain house prices
