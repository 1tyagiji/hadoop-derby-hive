----Commands Used-----

hdfs namenode -format //format hdfs....to be done once only

start-all   //start hadoop

mapred historyserver //to start history server for mapreduce jobs

startnetworkserver -h 0.0.0.0   //to start networkserver

hive --service schematool -dbType derby -initSchema  //to be done only once to initialise metastore

hive --service hiveserver2 start

hive


stopnetworkserver

stop-all

----------


Note - You don't have to change the directory to use these commands as we have already declared paths in system variables....And always start hive from same directory

First delete your previous hadoop and hive
Now uninstall your previous java installation











Download - Java 1.8 and install it in C:\Java
also install jre in C:\Java\jre1.8.0_281


Download - Hadoop - 3.3.0 and extract it in C:\hadoop

Download - Apache Derby 10.14.2.0 and extract it in C:\hadoop\derby


Download - Apache Hive 3.1.2 and extract it in C:\hadoop\hive


Download https://github.com/1tyagiji/hadoop-derby-hive and extract it anywhere

Install all the MVC++

now run setx.bat as administrator


Now copy this hadoop folder and paste it in C:\


Now we need to set the environment variables








Copy this and paste it to system Path variable

%HADOOP_HOME%\bin;%HADOOP_HOME%\sbin;%JAVA_HOME%\bin;%HIVE_BIN%;%DERBY_HOME%\bin;%HIVE_HOME%;


Now we are going to copy all derby\lib\ files to hive lib



Copy guava-ver.jar from C:\hadoop\share\hadoop\hdfs\lib and paste it to C:\hadoop\hive\lib

delete prexisting guava-19.0.jar and rename new file to guava-19.0.jar


Now we are all set to start our hadoop and hive

Lets begin

Remember always run cmd as admin


we need to format namenode only once

after doing it once....directly start hadoop using start-all command


but if you format namenode 2nd time by mistake then you have to go to


C:\hadoop\data\dfs\data_330

and delete all files here


and then start hadoop
make sure no daemon shuts down....if any shuts down...then there is some problem with you installation


to check if all nodes are working fine...you can go to

localhost:8088
localhost:9870
localhost:9864


In windows we need to start historyserver also for any mapreduce job
by this command


Now lets try to start hive

before running schematool to initialise derby db check if you have any folder named metastore_db in your C:\WINDOWS\system32 folder

if yes then delete it first

now start the command

you need to initialise the derby from schematool only once as we did in case of hdfs namenode -format


from next time just start hiveserver 2 after starting hive


Let it get completed



Now start hiveserver2



#you can check webUI of hiveserver2 on

#localhost:10002

after it gets started



now lets start hive


our hive server is started



now let me show you how to shut down hive and again restart it successfully


to shut down hive server2  go to that cmd and press ctrl+c


now turn off the mapred historyserver in same way



to turn of network server use this command


now stop hadoop


now lets start it once again



Thankyou
