
# Datamizer for Python  
[![PyPI version](https://badge.fury.io/py/datamizer.svg)](https://badge.fury.io/py/datamizer)

This is a simple package that lets you change the sensitive data from a .CSV file creating a new file with fake data.  
  
  
This allows the new data to be used for training, testing or analytics, without compromising private information.  
  
## Installation  
  
Run the following command to install the package:  
```  
pip install datamizer  
```  
  
## Usage

1- Instanciate the Datamizer class, pass the path to the CSV file, and optionally the CSV delimiter.
```python  
from datamizer import Datamizer

csv_datamize = Datamizer('file.csv')
```  
2- Use `fake()` to anonymize the columns with sensitive data, passing the `column`,`provider`, and optionally `consistent` args.
```python
csv_datamize.fake('Username', 'user_name', consistent=True)
csv_datamize.fake('First name', 'first_name', consistent=True)
csv_datamize.fake('Last name', 'last_name', consistent=True)
csv_datamize.fake('email', 'email', consistent=True)
csv_datamize.fake('Money', 'pricetag')
```
3- Write a new CSV file with the fake data, passing the path to the new file and optionally `index=True` to include the index.
```python
csv_datamize.write_csv('users.csv')
```
