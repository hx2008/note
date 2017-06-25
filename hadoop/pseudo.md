Make directories
```
mkdir /home/fushikai/hddata
cd /home/fushikai/hddata
mkdir data name tmp
```
core-site.xml
```
<configuration>
    <property>
        <name>fs.defaultFS</name>
        <value>hdfs://localhost:9000</value>
    </property>
    <property>
        <name>hadoop.tmp.dir</name>
        <value>/home/fushikai/hddata/tmp</value>
    </property>
</configuration>
```
hdfs-site.xml
```
<configuration>
  <property>
    <name>dfs.namenode.name.dir</name>
    <value>/home/fushikai/hddata/name</value>
  </property>
  <property>
    <name>dfs.datanode.data.dir</name>
    <value>/home/fushikai/hddata/data</value>
  </property>
  <property>
    <name>dfs.replication</name>
    <value>1</value>
  </property>
</configuration>
```
mapred-site.xml
```
<configuration>
  <property>
    <name>mapreduce.framework.name</name>
    <value>yarn</value>
  </property>
</configuration>
```
yarn-site.xml
```
<configuration>
  <property>
    <name>yarn.nodemanager.aux-services</name>
    <value>mapreduce_shuffle</value>
  </property>
  <property>
    <name>yarn.nodemanager.aux-services.mapreduce_shuffle.class</name>
    <value>org.apache.hadoop.mapred.ShuffleHandler</value>
  </property>
  <property>
    <name>yarn.resourcemanager.hostname</name>
    <value>localhost</value>
  </property>
</configuration>
```
Commands
```
$ hdfs namenode -format
$ start-dfs.sh
$ start-yarn.sh
$ hdfs dfsadmin -report
$ jps
$ hadoop jar $HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-examples-2.2.0.jar pi 10 20
```
Urls
```
http://localhost:50070/
```
