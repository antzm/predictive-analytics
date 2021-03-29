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

### Linear Regression using Excel

In Excel we can easily create a scatter plot for a predictor and a target variable and then add the linear regression line on the graph.

Somethimes though, our data is in CSV (comma separated values) format, and it could be time consuming to import that data in Excel, espeially if the data are formated in e.g. US number format and they need to be analyzed on a computer using European number format.

Thus, the easiest approach to convert a CSV file to Excel, is to use a Jupyter Notebook and a few lines of code. 

Not everyone one though has a Jupyter Notebook server running on their computers, and for this reason, below is a simple approach than can be used on any computer to easily convert a CSV file to an Excel file:

First, we should login to our Google account

Then, we use Google search and search for: google colab

We click on the first result and then, on the popup window we select "New Notebook"

Then, in the code cells of the notebook, we run the following code:

```python
#Code cell 1:
# Import libraries and modules
import pandas as pd
from google.colab import files

#Code cell 2:
# Uploading the CSV file (e.g. my_uploaded_file.csv)
files.upload()

#Code cell 3:
# Importing the CSV file to a Pandas DataFrame
# and assuming that the separator is a comma and the decimal point is a dot
my_data = pd.read_csv("my_uploaded_file.csv", sep=',', header=0, decimal='.', encoding='utf_8')

#Code cell 4:
# Exporting the Pandas DataFrame to an Excel file
my_data.to_excel("my_output_file.xlsx", header=True, index=False)

#Code cell 4:
# Downloading the Excel file
files.download('my_output_file.xlsx')

```
