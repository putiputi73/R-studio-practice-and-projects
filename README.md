# R-studio-practice-and-projects
Creating random x and Y values then calculating linear regression and test statistics
##
# Load the generated data
data <- data.frame(x = 1:10, y = rnorm(10))

# Create a linear regression model
model <- lm(y ~ x, data = data)

# Display the model summary
summary(model)

# Calculate the test statistic for the slope coefficient
t_stat <- coef(model)["x"] / sqrt(summary(model)$coefficients[2, 2])
cat("The t-statistic for the slope coefficient is", round(t_stat, 2))

## Results
Call:
lm(formula = y ~ x, data = data)

Residuals:
     Min       1Q   Median       3Q      Max 
-1.34642 -0.49252 -0.01642  0.48016  1.33718 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)  
(Intercept) -0.72562    0.35215  -2.061   0.0541 .
x            0.06423    0.02940   2.185   0.0424 *
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.7581 on 18 degrees of freedom
Multiple R-squared:  0.2096,	Adjusted R-squared:  0.1657 
F-statistic: 4.773 on 1 and 18 DF,  p-value: 0.04237
