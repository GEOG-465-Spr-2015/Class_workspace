#GEOG 465 Glossary of Terms
Put your descriptions below. IF you have never used markdown for formatting, check out [this resource](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

##ArcPy
ArcPy is a set of tools and arguments used by ESRI in order to execute geoprocessing functions.
It is appendable to a classic Python script, and can be used inside and outside of ArcMap.
To access it outside of ESRI products, use the code 'import arcpy'.
It is used, in many cases, to automate iterative analysis
An example of arcpy use is creating a buffer around every single line that represents roads, in order to find
Potential risk areas for endangered snails.
You can use ArcPy in lieu of ArcModelBuilder
Below is an example of this:
```
# Name: Snap.py
# Description: Snap climate regions boundary to vegetation layer
#              boundary to ensure common boundary is coincident


# import system modules 
import arcpy

# Set environment settings
arcpy.env.workspace = "C:/data"

# Make backup copy of climate regions feature class, 
# since modification with the Editing tools below is permanent
climateBackup = "backups/climate.shp"
arcpy.CopyFeatures_management('climate.shp', climateBackup)

# Densify climate regions feature class to make sure there are enough
#vertices to match detail of vegetation layer when layers are snapped
arcpy.Densify_edit('climate.shp', "DISTANCE", "10 Feet") 

# Snap climate regions feature class to  vegetation layer vertices and edge
# first, snap climate region vertices to the nearest vegetation vertex within 30 Feet
# second, snap climate region vertices to the nearest vegetation edge within 20 Feet

snapEnv1 = ["Habitat_Analysis.gdb/vegtype", "VERTEX", "30 Feet"]    
snapEnv2 = ["Habitat_Analysis.gdb/vegtype", "EDGE",   "20 Feet"]       
arcpy.Snap_edit('climate.shp', [snapEnv1, snapEnv2])
```
=======

ArcPy is a set of tools and arguments used by ESRI in order to execute geoprocessing functions. It is appendable to a classic Python script, and can be used inside and outside of ArcMap. To access it outside of ESRI products, use the code 'import arcpy'. It is used, in many cases, to automate iterative analysis
>>>>>>> origin/master

##Code

##Data

##Data types

You can store numbers in one of four numeric data types: Short integer,Long integer, Float (single-precision floating-point numbers),Double (double-precision floating-point numbers)
```
Data types in the DBMS
OBJECTID: Long Integer
SHORT INTEGER:Integer
```

##Control flow statements

First of all, control flow is the order in which the file will execute. Typically, this will be from the top to the bottom.

Control flow statements alter the order in which the code is executed. These types of statements include
	if/else statements,
	for loops,
	while loops,
	break statements
```
count=0
for i in 10:
	count+=1
print count
```
In this example, it will go through lines 1-3 directly, but since there is a for loop from lines 2-3, it will return to this loop rather than proceed onto line 4. Once the loop is complete, it will move on with the rest of the code.

##Function

A function is a defined, organized, reusable block of code that performs a single, related action. Functions often take in values as parameters and return values as output. Functions are declared using the following syntax:

```
def myFunctionName(param1, param2):
  function code goes here
  return something, call another function, etc. 
  
outside the scope of the function
```

##List Comprehension

A list comprehension is a compact way to map one list into another without changing the original list. The feature works by applying a function to each element of the list being mapped. This allows python to loop through the list one element at a time. In the process, python temporarily assigns the value of each of these elements to a designated variable (such as “elem”) before applying a function (such as “elem*2”) and appending this result to the list that is returned.

```
>>> list = [1, 2, 3, 4, 5, 10]
>>> list
[1, 2, 3, 4, 5, 10]
>>> [elem*2 for elem in list]
[2, 4, 6, 8, 10, 20]
```

One may also safely choose to assign the result of a list comprehension to the variable being mapped.

```
>>> list = [1, 2, 3, 4, 5, 10]
>>> list
[1, 2, 3, 4, 5, 10]
>>> list = [elem*2 for elem in list]
>>> list
[2, 4, 6, 8, 10, 20]
```

##Geoprocessing

Geoprocessing is a large variety of operations that uses input data to generate meaningful output data in ArcGIS (or other GIS software).
It deals with spatial data, with a geographic coordinate system.
An example is the use of the raster calculator/map algebra tool to generate a suitability model. For instance, to find ideal park sites, the following formula can be used:

```
Population Density > x * Distance to Parks < y = Ideal Park Sites
```

##Loop
Piece of code which you want to repeat n number of times 

When you have a piece of code you want to run x number of times, then code within that code which you want to run y number of times, you use what is known as a "nested loop". 

Can use functions such as "if", "elif", and "else"

Ex.
```
for x in xrange(3):
    print x
else:
    print 'Final x = %d' % (x)
```
##Software

##Try/Except

Try/Except is a way to handle possible errors which the program or interface might experience. 

It will try the user's answer to the prompt, for example, then if the users prompt is invalid it will

handle it as an error instead of the user's input breaking the code, and forcing the code to stop running. 

##If/Else if/Else statements
This is used to decide whether to do something at a special point, or to decide between two courses of action.
The following test decides whether a student has passed an exam with a pass mark of 45

```if (result >= 45)
        printf("Pass\n");
else
        printf("Fail\n");```
It is possible to use the if part without the else.

```if (temperature < 0)
        print("Frozen\n");```
Each version consists of a test, (this is the bracketed statement following the if). If the test is true then the next statement is obeyed. If is is false then the statement following the else is obeyed if present. After this, the rest of the program continues as normal.
If we wish to have more than one statement following the if or the else, they should be grouped together between curly brackets. Such a grouping is called a compound statement or a block.


```if (result >= 45)
{       printf("Passed\n");
        printf("Congratulations\n")
}
else
{       printf("Failed\n");
        printf("Good luck in the resits\n");
}```
Sometimes we wish to make a multi-way decision based on several conditions. The most general way of doing this is by using the else if variant on the if statement. This works by cascading several comparisons. As soon as one of these gives a true result, the following statement or block is executed, and no further comparisons are performed. In the following example we are awarding grades depending on the exam result.

```if (result >= 75)
        printf("Passed: Grade A\n");
else if (result >= 60)
        printf("Passed: Grade B\n");
else if (result >= 45)
        printf("Passed: Grade C\n");
else
        printf("Failed\n");```
In this example, all comparisons test a single variable called result. In other cases, each test may involve a different variable or some combination of tests. The same pattern can be used with more or fewer else if's, and the final lone else may be left out. It is up to the programmer to devise the correct structure for each programming problem.

##With Statement

The with statement is useful when there are two related operations that are executed as a pair, with a block of code between them. A simple example of a use of this statement is to open a file, manipulate it, then close the file:

```python
with open('output.txt', w) as f
  f.write('Hello!')
```

The above with statement will automatically close the file after the nested block of code. This is an advantage of with statements: the file is guaranteed to close, no matter how the nested block exits.

##Split
The split function separates a single string into a string array using a defined separator.
If there is no separator defined, it will separate by space.

```python
line = "a,b,c,d,5,6,7"
list = line.split(",")

print list
print list[5]
```

The result should look like this
['a', 'b', 'c', 'd', '5', '6', '7']
6
 
##STRIPS

##Read/Write Statements

##Lambda functions

Lambda functions are one-line mini functions that can be defined on the fly within a script. They return any number of arguments (including optional ones) as the value of a single expression. They can be used anywhere that a function is required, but cannot contain commands or multiple expressions. Below, the regular function is followed by a lambda function, which accomplishes the same function.

```
>>> def f(x):
	return x*2

>>> f(5)
10
>>> g = lambda x: x*2
>>> g(5)
10
```

The lambda function is able to utilize abbreviated syntax (it does not include parentheses or the return keyword, which is implied, as the regular function does). Lambda functions can be called through the variable to which it is assigned (though it does not require being assigned to a variable). Here is an example:

```
>>> (lambda x: x*2)(5)
10
```

Utilization of lambda functions could be seen as advantageous in situations calling for one-time use of code, as it can prevent extraneous one-line functions.

##Tuples 
A tuple is a sequence of immutable Python objects. 
Tuples are sequences, just like lists.
The only difference is that tuples can't be changed i.e., tuples are immutable and tuples use parentheses and lists use square brackets.
```tup1 = ();
```tup1 = (50); 

##While Loops
Unlike for loops, while loops will continue to run while the condition still holds true.

```
list = ["a","b","c","d","e"]
i=0
while list[i]!="d":
    print list[i]
    i+=1
```
This while loop will run until the item in the list is not equal to the string, "d".
