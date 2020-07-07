# Big Data Hadoop System: Project Overview (with Chunchu Liu and Yuke Liu)

## Part 1: Setting up Hadoop

We set up the yarn-sit.xml, core-site.xml, hdfs-site.xml, and mapred-site.xml to build up the cluster in hadoop. Starting up the yarn services and hdfs servises by using the following command:
`start-all.sh`

In master, we get the jps in below:

![master.png](https://github.com/ILing82816/ds_hadoop_proj/blob/master/Figure/master.png)

In slave1 and slave2, we get the jps in below:

![slave1.png](https://github.com/ILing82816/ds_hadoop_proj/blob/master/Figure/slave1.png)

![slave2.png](https://github.com/ILing82816/ds_hadoop_proj/blob/master/Figure/slave2.png)

We use Dockfile in the zip to build up the Docker container. And successfully run the wordcount.


## Part 3: Developing a Hadoop program

We use ngram.java to produce the n-gram frequencies. 

- First, we need to compile the programming:  
    `hadoop com.sun.tools.javac.Main ngram.java`    
- If the programming don't have error, we package the programming to jar:  
    `jar cf ngram.jar ngram*.class`  
- we build up a file folder and put input file in it:  
    `hadoop fs -mkdir project1/inputfile`    
    `hadoop fs -put input inputfile`  
- we execute the jar and put the output in outputfile:  
    `hadoop jar ngram.jar ngram project1/inputfile outputfile`  

Our output is down below:  

![output1.png](https://github.com/ILing82816/ds_hadoop_proj/blob/master/Figure/output1.png)

## Part 4: Developing a Hadoop program to analyze real logs 

We use logAnalyze1.java to analyze a real anonymous logs to answer "How many hits were made to the website item “/assets/img/home-logo.png”?". 

- First, we need to compile the programming. `hadoop com.sun.tools.javac.Main logAnalyze1.java` 
- If the programming don't have error, we package the programming to jar. `jar cf logAnalyze1.jar logAnalyze1*.class` 
- we build up a file folder and put input file in it. `hadoop fs -mkdir inputfile2` `hadoop fs -put access_log inputfile2` 
- we execute the jar and put the output in outputfile. `hadoop jar logAnalyze1.jar logAnalyze1 inputfile2 project1result7`  

Our output:

![output41.png](https://github.com/ILing82816/ds_hadoop_proj/blob/master/Figure/output41.png)

We use logAnalyze.java in the zip to analyze a real anonymous logs to answer "How many hits were made from the IP: 10.153.239.5?". 

- First, we need to compile the programming. `hadoop com.sun.tools.javac.Main logAnalyze.java` 
- If the programming don't have error, we package the programming to jar. `jar cf logAnalyze.jar logAnalyze*.class` 
- we build up a file folder and put input file in it. `hadoop fs -mkdir inputfile2` `hadoop fs -put access_log inputfile2` 
- we execute the jar and put the output in outputfile. `hadoop jar logAnalyze.jar logAnalyze inputfile2 project1result4`  

Our output:

![output42.png](https://github.com/ILing82816/ds_hadoop_proj/blob/master/Figure/output42.png)

We use logAnalyze3.java in the zip to analyze a real anonymous logs to answer "Which path in the website has been hit most? How many hits were made to the path?". 

- First, we need to compile the programming. `hadoop com.sun.tools.javac.Main logAnalyze3.java` 
- If the programming don't have error, we package the programming to jar. `jar cf logAnalyze3.jar logAnalyze3*.class` 
- we build up a file folder and put input file in it. `hadoop fs -mkdir inputfile2` `hadoop fs -put access_log inputfile2` 
- we execute the jar and put the output in outputfile. `hadoop jar logAnalyze3.jar logAnalyze3 inputfile2 project1result9`  

Our output:

![output3.png](https://github.com/ILing82816/ds_hadoop_proj/blob/master/Figure/output3.png)

We use logAnalyze4.java in the zip to analyze a real anonymous logs to answer "Which IP accesses the website most? How many accesses were made by it?". 

- First, we need to compile the programming. `hadoop com.sun.tools.javac.Main logAnalyze4.java` 
- If the programming don't have error, we package the programming to jar. `jar cf logAnalyze4.jar logAnalyze4*.class`
- we build up a file folder and put input file in it. `hadoop fs -mkdir inputfile2` `hadoop fs -put access_log inputfile2` 
- we execute the jar and put the output in outputfile. `hadoop jar logAnalyze4.jar logAnalyze4 inputfile2 project1result10`  

Our output:

![output44.png](https://github.com/ILing82816/ds_hadoop_proj/blob/master/Figure/output44.png)
