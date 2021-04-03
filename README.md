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
# either sep=',' or sep=';' or sep=' ' or sep='\t' depending on the separator or delimiter
# header=0 if there are headers on the first row or header=None if there re no headers
# decimal='.' or decimal=','

#Code cell 4:
# Exporting the Pandas DataFrame to an Excel file
my_data.to_excel("my_output_file.xlsx", header=True, index=False)
# header=True for including the headers in the Excel file
# index=False for not including an index column (0, 1, 2, 3...)

#Code cell 4:
# Downloading the Excel file
files.download('my_output_file.xlsx')

```

When using this code on a local computer, the part for importing the Google module and the parts for uploading and downloading the files, can be ommited and the code can be simplified to:

```python
# Importing the Pandas library
import pandas as pd

# Importing the CSV file to a Pandas DataFrame
# and assuming that the separator is a comma and the decimal point is a dot
my_data = pd.read_csv("my_uploaded_file.csv", sep=',', header=0, decimal='.', encoding='utf_8')
# either sep=',' or sep=';' or sep=' ' or sep='\t' depending on the separator or delimiter
# header=0 if there are headers on the first row or header=None if there re no headers
# decimal='.' or decimal=','

# Exporting the Pandas DataFrame to an Excel file
my_data.to_excel("my_output_file.xlsx", header=True, index=False)
# header=True for including the headers in the Excel file
# index=False for not including an index column (0, 1, 2, 3...)

```

## A/B Testing

A/B Testing is a term used in the context of business but the more general scientific term is Hypothesis Testing. We could say that A/B Testing is the simplified approach used when testing something (i.e. performing an experiment) in a busindess environment.

It is a predictive approach used whenever we don't have historical data to help us make a business decision and thus, we need to perform an experiment in order to collect that neccesary data.

When performing an A/B Testing, we have a Control Group and a Treatemnt Group.

* Control Group, i.e. the Existing Business Situation
* Treatment Group i.e., the new business situation we would like to test, or compare, with the existing situation

There two approaches to conduct an A/B Test. Either by using a Randomized Design or by using a Matched Pair Design:

* Randomized Design
	* Treatment Unit, randomly chosen
	* Control Unit, randomly chosen

* Matched Pair Design
	* Treatment Unit, paired with a control unit
	* Control Unit, paired with a treatment unit

In order for the results to be valid, the experiment for both the control and the treatment units should take place under the same conditions. Obviously, in most cases this is almost impossible, so we are trying at least to pinpoint the most important factors that we need to take into consideration in order to create similar conditions for bothe the contorol and the treatment units.

Those factors which are responsible for creating similar conditions, are called control variables and before conducting an experiment we should be able to identify the most important control variables so that we will be able to create similat conditions, as musch as possible. for our experiment.
