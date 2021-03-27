# Udacity-Bertelsmann Predictive Analytics Program

**Introduction**

Analyzing a few of the concepts that are presented during the courses of the Predictive Analytics Program

## Linear Regression

Linear regression is a mathemacical approach that helps us understand how one variable affects another variable.

In the simplest form, we consider two variables, an independent variable and a dependent variable. If the relationship betweend those two variables is a linear relationship, then we can proceed with the linear regression.

Then, we calculate an equation of a line that describes the way that one vriable affects the other variable.

If though the relationship between those two variables is not a linear relationship, which can be revealed by creating a scatter plot, then we cannot use linear regression in this case because we have a non linear relationship.

In a similar way, if more than one independent variables (or predictor variables) affect our dependent variable (or target variable) in a linear way, then we use multi linear regression.

When we have two independent variables affecting our dependent variable, then the equation of the multi linear regression is the equation a plane in the 3-D axis system.

If though we have more than two independent variables that affect our dependent variable, then the multi linear regression is represented by a hyper plane in the n-th dimensional space.

### The method of Ordinary Least Squares (OLS)

When building a regression model, with one predictor and one target variable, we need to find a line that best describes the linear relationship between those two variables.

And this line needs to be calculated in an objective way, otherwise each data analyst or data scientist will draw a line based on their own perception which is something subjective.

Thus, to calculate in an objective way the regression line, we need to calculated the distance of each point in the scatterplot from the regression line. Then, using the proper mathematical tools, we try to minimize that value, which measn that the line is the best fit for all the data.

To avoid mistakes by positive and negative values summing up to zero, we raise to the square each distance, between a point and the regression line,, and then we try to minimize the sum of those squared values. For this reason, the method is called method of the OLS (ordinary least squares).
 