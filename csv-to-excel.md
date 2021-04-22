# Converting a CSV file to an Excel file

Sometimes it can be complicated and time consuming to import CSV data to Excel. Especially whenever there is a CSV file containing decimal numbers in a different format, than the one we are using based on our regional settings.

In such a case, it's much simpler to convert the CSV file to an Excel file using Python and Pandas.

The following approach though, uese Google Colab for the conversion, instead of a local Jupyter Notebook.

This way, the conversion can take place on any computer by just using a browser:


```python

# Converting a csv file to an excel file using:
# https://colab.research.google.com

# Instructions:
# Login to your Google ac account and search for: google colab
# click on the first result, choose "new notebook"
# and use CTRL+V to paste and then run the following code:

# Import libraries and modules
import pandas as pd
from google.colab import files

# Uploading the CSV file
uploaded = files.upload()

# Extracting the file name from the dictionary "uploaded" which contains
# one key with the file name and one value with the content of the file
for key in uploaded.keys():
  my_uploaded_file = key

# Importing the CSV file to a Pandas DataFrame
# sep=',' or sep=';' or sep=' ' or sep='\t'
# decimal='.' or decimal=','
# header=0 or header=None
my_data = pd.read_csv(my_uploaded_file, sep=',', header=0, decimal='.', encoding='utf_8')

# Exporting the Pandas DataFrame to an Excel file
# header=True to include the headers
# index=False for not including the column index (0, 1, 2...)
my_data.to_excel("my_output_file.xlsx", header=True, index=False)

# Downloading the Excel file
files.download('my_output_file.xlsx')

# Before closing your notebook:
# From the edit menu, delete all output
# Click on the folder icon on the left side,  
# and delete your csv and excel file. 
# Save your notebook as e.g. csv-to-excel
# Next time you need to convert a csv file,
# just open this notebook and run the cells.

```

This process can be used for any CSV file, regardless if it has a .csv or a .txt extension. The pandas.read_csv() method, reads any file (regardless of extenion) that contains data in the form of a CSV file.

Although CSV actually statnds for Comma Seperated Values, in reality the same name is used regardless if the separatoer is comma, semicolon, space, tab or something else.

Thus, regardless of the separator used in a CSV file, the Pandas library will read correctly the file provided we have enter as an argument the correct separator for that file.
  
Although it's not mentioned in the above code, we could also use the `my_data.head()` method, after importing our CSV file, to verify that the CSV file has been correctly imported to oud dataframe. Otherwise, we should do any neccesary changes to the arguments used while reading a CSV file and then to read the file for a second time.
