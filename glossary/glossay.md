#GEOG 465 Glossary of Terms
Put your descriptions below.

##ArcPy
ArcPy is a set of tools and arguments used by ESRI in order to execute geoprocessing functions.
It is appendable to a classic Python script, and can be used inside and outside of ArcMap.
To access it outside of ESRI products, use the code 'import arcpy'.
It is used, in many cases, to automate iterative analysis
Code

##Data

##Data types

##Control flow statements

##Function

##Geoprocessing
Geoprocessing is a large variety of operations that uses input data to generate meaningful output data in ArcGIS (or other GIS software).
It deals with spatial data, with a geographic coordinate system.
An example is the use of the raster calculator/map algebra tool to generate a suitability model. For instance, to find ideal park sites, the following formula can be used:
Population Density > x * Distance to Parks < y = Ideal Park Sites

##Loop

##Software

##Try/Except
Try/Except is a way to handle possible errors which the program or interface might experience. 
It will try the user's answer to the prompt, for example, then if the users prompt is invalid it will
handle it as an error instead of the user's input breaking the code, and forcing the code to stop running. 

#If/Else if/Else statements

##With Statement
The with statement is useful when there are two related operations that are executed as a pair, with a block of code between them. A simple example of a use of this statement is to open a file, manipulate it, then close the file:

with open('output.txt', w) as f
  f.write('Hello!')

The above with statement will automatically close the file after the nested block of code. This is an advantage of with statements: the file is guaranteed to close, no matter how the nested block exits.
