# HoleFoodsAdaptiveAnalyticsSample
## Overview
Easy way to import the HoleFoods Sample data into InterSystems IRIS and a sample AtScale model using the AtScale Sample Bundle

# Installing the Sample
## Prep IRIS before loading the sample
1) Make sure you have the ***MySample*** schema defined in the IRIS namespace you want to import the sample into 
2) If the schema is not defined, run the following SQL in the SMP:
*  _CREATE TABLE MySample.Dummy (P1 INT NOT NULL)_
3) If you want to also set up some global mappings, insert at least 1 row so you can find out the global hash that needs to be mapped
*  _INSERT INTO MySample.Dummy (P1) VALUES (1)_

## In AtScale, log in and go to the PROJECTS tab
1) Click on the hamburger menu icon and select "Use a sample"

    ![image](https://user-images.githubusercontent.com/30053816/115746186-1f2b8380-a362-11eb-8f03-517df862e63d.png)

2) Select your DWH, the MySample schema, and the zip file
3) Default permissions can be used

**You should expect new tables in IRIS and a new Project in AtScale!**

# For Contributors 
## The files 
The **manifest.json** file controls the data files and project files also and describes the delimiters

The **/MySample/data** folder holds all the tables that will be imported into IRIS. Each folder will hold a file with the data (please note that there are no headers in the \<table name\>.csv **comma delimited** file)

![image](https://user-images.githubusercontent.com/30053816/115742298-87786600-a35e-11eb-8b54-ecc2d65f8ee6.png)

The **/MySample/project** folder will hold the project file that will contain the following:
* Cube definitions
* Source table metadata
  * In the \<data-set\> tags
  * Maps to data files
  * Can control the names of the tables and columns

## Creating a new Project zip
Once you have made your changes you will need to zip up the files. To create the zip file, the top level MySample directory and manifest.json should be zipped together.

![image](https://user-images.githubusercontent.com/24307254/121373511-20624100-c90d-11eb-964a-bd0aee369283.PNG)




