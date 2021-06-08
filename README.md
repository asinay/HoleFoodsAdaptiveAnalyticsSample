# HoleFoodsAdaptiveAnalyticsSample
## Overview
Easy way to import the HoleFoods Sample data into IRIS and a sample AtScale model using the AtScale Sample Bundle

## The files 
The **manifest.json** file controls the data files and project files also and describes the delimiters

The **/MySample/data** folder holds all the tables that will be imported into IRIS. Each folder will hold a file with the data (please note that there are no headers in the \<table name\>.csv **comma delimited** file)

![image](https://user-images.githubusercontent.com/30053816/115742298-87786600-a35e-11eb-8b54-ecc2d65f8ee6.png)

The **/MySample/project** folder will hold the project file that will contain the following:
1. Some metadata about the AtScale version publish date
2. The AtScale project
3. The tables metadata in the \<data-set\> where you can control the names of the tables and columns


Once you have made your changes you will need to zip up the files and place the zip file in the directory where the manifest file resides:

![image](https://user-images.githubusercontent.com/30053816/115744442-919b6400-a360-11eb-9377-a47fa2955c0e.png)

## Example: Importing the HoleFoods Sample into the MySample package
#### Prep before loading the sample into IRIS
Make sure you have the schema defined in IRIS in the namespace you want to import it to 

#### Run the following SQL in the SMP:
  _CREATE TABLE MySample.Dummy (P1 INT NOT NULL)_
  
If you want to also set up some global mappings, insert at least 1 row so you can find out the global hash that needs to be mapped
  _INSERT INTO MySample.Dummy (P1) VALUES (1)_

#### In AtScale, log in and go to the PROJECTS tab
Click on the sandwitch menu and select Use a sample

![image](https://user-images.githubusercontent.com/30053816/115746186-1f2b8380-a362-11eb-8f03-517df862e63d.png)

Select your DWH and the MySample schema and the zip file; if there are no errors reported, you are done!  
**You should expect new tables in IRIS and a new Project in AtScale!**




