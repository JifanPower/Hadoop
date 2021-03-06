# Hadoop Basic

## Prerequisites
* **Linux Basic**
* **Java[Option]**
* **Sql[Option]**

## Hadoop Origin
    Google
        GFS          ->     HDFS
        MapReduce    ->     MapReduce
        BigTable     ->     HBase
Hadoop was created by Doug Cutting, the creator of Apache Lucene, the widely used text search library. Hadoop has its origins in Apache Nutch, an open source web search engine, itself a part of the Lucene project.

## Hadoop Modules
* **Hadoop Common**: The common utilities that support the other Hadoop modules.
* **Hadoop Distributed File System (HDFS™)**: A distributed file system that provides high-throughput access to application data.
* **Hadoop YARN**: A framework for job scheduling and cluster resource management.
* **Hadoop MapReduce**: A Y   ARN-based system for parallel processing of large data sets.

## Hadoop-Related Projects 
* **HBase™**: A scalable, distributed database that supports structured data storage for large tables.
* **Hive™**: A data warehouse infrastructure that provides data summarization and ad hoc querying.
* **ZooKeeper™**: A high-performance coordination service for distributed applications.

## Hadoop Directory
    /etc    config files
    /bin    executable files
    /sbin   sh files
    ...

## Hadoop Modules
    HDFS
        namenode
        datanode
        secondary namenode

    YARN
        resource manager
        node manager

    MapReduce
        map
        reduce

## Hadoop Modules Introduce
* ### HDFS(Hadoop Distributed File System)
    HDFS is a distributed filesystem designed for storing very large files with streaming data access patterns, running on clusters of commodity hardware.
    
    **namenode**  
    It maintains the filesystem tree and the metadata for all the files and directories in the tree.

    **datanode**  
    Datanodes are the workhorses of the filesystem. 
    They store and retrieve blocks when they are told to (by clients or the namenode), and they report back to the namenode periodically with lists of blocks that they are storing.

    **secondary namenode**  
    Its main role is to periodically merge the namespace image with the edit log to prevent the edit log from becoming too large.

* ### YARN(Yet Another Resource Negotiator)
    It is Hadoop’s cluster resource management system.
    
    **resource manager**  
    Resource manager manage the use of resources across the cluster.

    **node manager**  
    Node managers running on all the nodes in the cluster to launch and monitor containers.

* ### MapReduce
    MapReduce is a programming model for data processing.
    MapReduce works by breaking the processing into two phases,Each phase has key-value pairs as input and output.
    (input) <k1, v1> -> map -> <k2, v2> -> combine -> <k2, v2> -> reduce -> <k3, v3> (output)

## Hadoop Modules Startup
    HDFS
        bin/hdfs dfs name –format
        sbin/hadoop-daemon.sh start namenode
        sbin/hadoop-daemon.sh start datanode
        sbin/hadoop-daemon.sh start secondarynamenode

    YARN
        sbin/yarn-daemon.sh  start  resourcemanager
        sbin/yarn-daemon.sh  start  nodemanager

    MapReduce
