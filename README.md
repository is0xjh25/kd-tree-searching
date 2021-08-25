# K-D Trees Map Search

## Purpose
• Increase your proficiency in C programming, your dexterity with dynamic memory allocation and your understanding of more advanced data structures (K-D trees).\
• Increase your understanding of how computational complexity can affect the performance of an algorithm by conducting orderly experiments with your program and comparing the results of your experimentation with theory.\
• Increase your proficiency in using UNIX utilities.

## Task & Requirements

### Dataset
Same dataset used in [Data Insertion and Searching](https://github.com/is0xjh25/data-insertion-searching)

### Stage 1
You will implement the basic functionality for an interactive map that allows a user to click on locations and retrieve data about the nearest point of interest. Instead of clicks, your code will accept (x,y) pairs from stdin, find the closest business establishment to that location in the dataset, and output the information about that establishment to a file.

Your Makefile should produce an executable program called map1. This program should take two command line arguments: (1) the name of the data file used to build the tree, and (2) the name of an output file.

Your map1 program should:\
• Construct a K-D tree to store the information contained in the data file specified in the command line argument. Each record (row) should be stored in a separate Node.\
• Handle duplicates (businesses located at exactly the same x,y coordinates) by chaining them together in a linked list connected to a single Node in the K-D tree. Exact duplicate locations should not be added as separate Nodes in the tree.\
• Accept locations queries from stdin and search the tree for the location nearest to the query point. The record(s) of the business(s) at this location should be printed to the output file. If there are multiple businesses at this location, all of them must be included in the output.\
• In addition to outputting the record(s) to the output file, the number of key comparisons per- formed during the search should be written to stdout.

### Stage 2
In stage 2, you will code a function that allows the user to find all of the business establishments within some distance of a query point. Your code will accept (x,y,radius) triplets from stdin, find all business establishments within the requested radius of the x,y point, and output the information about those establishments to a file.
Your Makefile should produce an executable program called map2. This program should take two command line arguments: (1) the name of the data file used to build the tree, and (2) the name of an output file

Your map2 program should:\
• Construct a K-D tree to store the information contained in the data file specified in the command line argument, exactly as in Stage 1. 
• Accept x,y,radius queries from stdin and search the tree for all locations within the requested radius of the x,y point. These records should be printed to the output file. When there are multiple businesses at the same location, all of these records should be included in the output.\
• If no business establishments are located with the query radius, your code must output the word NOTFOUND.\
• In addition to outputting the above data to the output file, the number of key comparisons performed during the search should be written to stdout.

### Stage 3
You will run various files through your program to test its accuracy and also to examine the number of key comparisons used when searching. We have provided a few different versions of the .csv file that can be used to build the tree. 
You should test your code with a variety of inputs and report on the number of key comparisons used by your code in Stage 1 and Stage 2. You will compare these results with each other and, importantly with what you expected based on theory (big-O).\
You will write up your findings and submit this report separately from your code. You should present your findings clearly, in light of what you know about the data structures used in your programs and their known computational complexity. 
Tables and/or graphs are recommended for presenting nu- meric results. You may find that your results are what you expected, based on theory. Alternatively, you may find your results do not agree with theory. 
In either case, you should state what you expected from the theory, and if there is a discrepancy you should suggest possible reasons.

_Report please see [Experimentation of K-D Tree map search](https://github.com/is0xjh25/kd-tree-searching/blob/main/1074004-Experimentation.pdf)_

---
### Command Line
map1 datafile outputfile < queryfile\
and\
map2 datafile outputfile < queryfile

### Example Output
#### _records in output.txt_
144.967058 -37.817313 0.0005 −−>Census year: 2018 || Block ID: 15 || Property ID: 109260 ||\
Base property ID: 109260 || CLUE small area: Melbourne (CBD) || Trading Name: Hungry Jack’s Pty Ltd ||\
Industry (ANZSIC4) code: 4511 || Industry (ANZSIC4) description: Cafes and Restaurants ||\
x coordinate: 144.9668 || y coordinate: -37.8171 || Location: (-37.81711586, 144.9668418) ||

144.967058 -37.817313 0.0005 −−>Census year: 2018 || Block ID: 15 || Property ID: 109258 ||\
Base property ID: 109258 || CLUE small area: Melbourne (CBD) || Trading Name: McDonalds ||\
Industry (ANZSIC4) code: 4511 || Industry (ANZSIC4) description: Cafes and Restaurants ||\
x coordinate: 144.9669 || y coordinate: -37.8172 || Location: (-37.81724484, 144.9669126) ||

#### _stdout_
144.967058 -37.817313 0.0005 −− > 678\
144.963089 -37.799092 0.0005 −− > 1356

---
_more details in project specification!_


