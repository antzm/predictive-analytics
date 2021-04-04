# Converting a CSV file to an Excel file


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