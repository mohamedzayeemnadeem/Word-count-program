### EX 6 A: Word Count Program Using Map And Reduce




## Aim:


To execute a Word Count Program Using Map And Reduce



## Procedure:

1.   Analyze the input file content
2.   Develop the code
a.   Writing a map function
b.   Writing a reduce function c.   Writing the Driver class
3.   Compiling the source
4.   Building the JAR file
5.   Starting the DFS
6.   Creating Input path in HDFS and moving the data into Input path
7.   Executing the program



## Program: WordCount.java





Step 1:  Compile the java program


For compilation we need this hadoop-core-1.2.1.jar file to compile the map reduce program.

https://mvnrepository.com/artifact/org.apache.hadoop/hadoop-core/1.2.1

Assuming both jar and java files in same directory run the following command to compile root@a4cseh160:/#javac -classpath hadoop-core-1.2.1.jar WordCount.java
Step 2: Create a jar file


Syntax:

jarcf jarfilename.jar MainClassName*.class

Output:

root@a4cseh160:/#jar cf wc.jar WordCount*.class

Step 3:  Make directory in hadoop file system


Syntax:

hdfsdfs -mkdirdirectoryname

Output:

root@a4cseh160:/# hdfsdfs -mkdir /user



Step 4:  Copy the input file into hdfs
Syntax:

hdfsdfs -put sourcefiledestpath

Output:

root@a4cseh160:/#hdfsdfs -put /input.txt /user

Step5:   To a run a program


Syntax:

hadoop jar jarfilenamemain_class_nameinputfileoutputpath





Output:

root@a4cseh160:/#hadoop jar wc.jar WordCount /user/input.txt /user/out



InputFile:      (input.txt)

Cloud and Grid Lab. Cloud and Grid Lab. Cloud Lab.

Output:

18

3          Cloud

3          Lab.

2          Grid

2          and





Step 6:  Check the output in the Web UI at  http://localhost:50070.
 



In the Utilities tab select browse file system and select the correct user. The output is available inside the

output folder named user.


















 Step 7:  To Delete an output folder
 



Syntax:

hdfsdfs -rm -R outputpath

Output:

root@a4cseh160:/#hdfsdfs -rm -R /user/out.txt














### Result:

Thus the numbers of words were counted successfully by the use of Map and Reduce tasks.









Review Questions:

1. What is Map?
	a programming model or pattern within the Hadoop framework that is used to access big data stored in the Hadoop File System (HDFS). 


2. What is Reduce?
	he reduce job takes the output from a map as input and combines those data tuples into a smaller set of tuples.



3. What is Hadoop core?
	Apache Hadoop is a framework that allows for the distributed processing of large data sets across clusters of commodity computers using a simple programming model.



4 What is HBase, Pig, Zooeeper and Hive?
	HBase - Is a NoSQL database on top of HDFS (hadoop distributed file system which is the file system and core component of Hadoop). Hive - Is an ecosystem/component of Hadoop which is similar to SQL to handle mostly structured data. Pig - Is an ecosystem/component of Hadoop which is a kind of scripting language

















































