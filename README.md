# cendas - About
cendas is a new pandas-based framework optimized for analyzing data provided by the U.S. Census Bureau and other U.S. government agencies.  The word "cendas" is a portmanteau of the words "census" and "pandas."  I was motivated to develop this python package from my experiences doing research at the Internet Real-Time Lab at Columbia University with Prof. Henning Schulzrinne.  Throughout the course of my research, I worked a lot with broadband adoption data provided by the Federal Communications Commission (FCC) and demographics data provided by the U.S. Census Bureau.  I oftentimes found myself using the same blocks of code over and over again on these datasets.  As a result, I thought it would be a good idea to put some of this code I used into a python package for the purposes of increasing workflow efficiency.  I also figured I probably wasn't the only one who would find this useful.  Please keep in mind this is still a work in progress.  If you have any questions, please feel free to reach out to me at jtk2141@columbia.edu.

# Installation

Please type in the following command into your command prompt.
```python
pip install cendas
```
OR

Download here: https://pypi.org/project/cendas/

# Documentation
```python
cendas.state_column(data_frame: pd.DataFrame(), tractcode_column: str)
```
The state_column function takes in a pandas dataframe and the column name of the column holding the census tract codes as arguments and creates a new "State" column in the dataframe populated with the U.S. state in which the census tract codes are located in.  The reason why I developed this function is because some datasets provided by some US government agencies only provide census tract codes with no reference to where exactly they are located.  

```python
cendas.state_abb_column(data_frame: pd.DataFrame(), tractcode_column: str)
```
The state_column function takes in a pandas dataframe and the column name of the column holding the census tract codes as arguments and creates a new "State Abbreviation" column in the dataframe populated with the U.S. state initials in which the census tract codes are located in.  The reason why I developed this function is the same as the above function -- some datasets provided by some US government agencies only provide census tract codes with no reference to where exactly they are located.  

