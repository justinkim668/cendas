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
The state_column function takes a pandas dataframe and the column name of the column holding the census tract codes as arguments and creates a new "State" column in the dataframe populated with the U.S. state in which the census tract codes are located in.  The reason why I developed this function is because some datasets provided by some US government agencies only provide census tract codes with no reference to where exactly they are located.  

```python
cendas.state_abb_column(data_frame: pd.DataFrame(), tractcode_column: str)
```
The state_abb_column function takes a pandas dataframe and the column name of the column holding the census tract codes as arguments and creates a new "State Abbreviation" column in the dataframe populated with the U.S. state initials in which the census tract codes are located in.  The reason why I developed this function is the same as the above function -- some datasets provided by some US government agencies only provide census tract codes with no reference to where exactly they are located.  

```python
cendas.conus_only(data_frame: pd.DataFrame(), tractcode_column: str)
```
The conus_only function takes a pandas dataframe and the column name of the column holding the census tract codes as arguments and drops rows in the dataframe where the census tracts are outside of the continental U.S.  This function returns a dataframe the displays only the censustracts within the continental U.S.  The reason why this function was developed was because there's always going to be stark statistical discrepancies between areas within the continental U.S. and outside of the continental U.S., especially when it comes to infrastructure-related matters.  

```python
cendas.oconus(data_frame: pd.DataFrame(), tractcode_column: str)
```
The oconus function takes a pandas dataframe and the column name of the column holding the census tract codes as arguments and only retains rows in the dataframe where the census tracts are located outside of the continental U.S.  This basically does the opposite of the conus_only function.

```python
cendas.geoid_to_tract(data_frame: pd.DataFrame(), geoid_column: str)
```
The geoid_to_tract function takes a pandas dataframe and the column name of the column holding the geoid codes as arguments and creates a new "tractcode" column in the dataframe with the census tract codes.  Several datasets provided by U.S. government agencies have a "geoid" column where all values start with '1400000US' followed by a census tract code.  This function effectively extracts the census tract codes from the geoid values.  
