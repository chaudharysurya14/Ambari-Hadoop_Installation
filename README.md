*Learning how to tame the Big Data with Hadoop and related technologies*

##### Table of Contents
- [Hadoop](#hadoop)
  * [Installation](#installation)
  * [Overview of Hadoop Ecosystem](#overview-of-hadoop-ecosystem)
  * [HDFS](#hdfs)
    + [Login using Ambari](#login-using-ambari)
    + [Login using Putty](#login-using-putty)
    + [Admin access for Ambari](#admin-access-for-ambari)
- [Map Reduce](#mapreduce)
  * [Architecture](#architecture)
  * [Handling Failures](#handling-failures)
  * [Map Reduce Example](#example)
  * [Running on HortonWorks Sandbox](#running-on-hortonworks-sandbox)
  * [Map Reduce Challenge 01](#map-reduce-challenge-01)
  * [Map Reduce Challenge 02](#map-reduce-challenge-02)
- [Pig](#programming-hadoop-with-pig)
  * [Pig Latin Example](#pig-latin-example)
  * [Running the script using Ambari](#running-the-script-using-ambari)
  * [Pig Latin: Diving Deeper](#pig-latin-diving-deeper)
  * [Pig Challenge](#pig-challenge-01)
- [Spark](#spark)
  * [Why is it scalable](#scalable)
  * [Components of Spark](#components-of-spark)
  * [Resilient Distributed Dataset (RDD)](#resilient-distributed-dataset-rdd)
    + [Creating RDDs](#creating-rdds)
	+ [Transforming RDDs](#transforming-rdds)
	+ [RDD Actions](#rdd-actions)
  * [Spark Example](#spark-example)
  * [Running the Spark script](#running-the-spark-script)
  * [Spark Challenge 01](#spark-challenge-01)
- [Spark SQL](#spark-sql)
  * [Shell access for Spark SQL](#shell-access)
  * [User defined functions](#spark-udfs)
  * [Spark SQL Example](#spark-sql-example)
  * [Running Spark SQL](#running-spark-sql)
  * [Spark SQL Challenge 01](#spark-sql-challenge-01)
- [Using MLLib in Spark 2.0](#using-mllib-in-spark-20)
  * [Making a recommendation model](#using-mllib-in-spark-20)
- [Hive](#hive)
  * [Why we use Hive](#why-hive)
  * [Where to not use Hive](#why-not-hive)
  * [HiveQL](#hiveql)
    - [HiveQL Example](#hiveql-example)
	- [How Hive works](#how-hive-works)
	- [HiveQL Challenge 01](#hiveql-challenge-01)
- [Sqoop](#sqoop)
  * [What is Sqoop](#sqoop)
  * [Transfer data to MySQL DB using Sqoop](#importing-movielens-data-into-a-mysql-db)
- [HBase](#hbase)
  * [HBase Architecture](#hbase-architecture)
  * [HBase Data Model](#hbase-data-model)
  * [How to access HBase](#some-ways-to-access-hbase)
  * [Populate HBase using Python REST API](#creating-a-hbase-table-with-python-via-rest)
  * [Integrate Pig with HBase](#integrating-pig-with-hbase)
- [Cassandra DB](#cassandra)
  * [So why Cassandra](#cassandras-design-choices)
  * [What is CQL](#cql)
  * [Cassandra and Spark](#cassandra-and-spark)
  * [Installing Cassandra](#installing-cassandra-on-horton-works-sandbox)
  * [Populate Cassandra DB with Spark](#populating-the-cassandra-db-with-spark)
- [Mongo DB](#mongodb)
  * [Does it have a schema](#no-real-schema-is-enforced)
  * [Lets learn Mongo terminology](#mongodb-terminology)
  * [How does it replicate](#replication-sets)
    - [Something we should know about Replica sets](#replica-set-quirks)
  * [Sharding](#sharding)
    - [Things to know about Sharding](#sharding-quirks)
  * [Mongo Extra knowledge](#neat-things-about-mongodb)
  * [How to use MongoDB with Spark](#using-mongo-with-spark-example)
  * [Example queries](#mongo-examples)

    
## Hadoop

* Hadoop is an **open source** software platform for **distributed storage** and **distributed processing** of **very large datasets** on **computer clusters** built from commodity hardware
* Why Hadoop?
  * Data is too big
  * Vertical scaling isn't an option
    * Disk seek times
    * Hardware failures
    * Processing times
  * Horizontal scaling is linear
  * You can do much more instead of just batch processing

## Installation
* Download Virtual Box from https://www.virtualbox.org/
* Download image of Hadoop to run on Virtual Box
  * (Horton Works Data Platform) **HDP 2.5 Sandbox** is preffered because it boots up faster than new versions
    * Download from https://hortonworks.com/downloads/#sandbox
* Import the image into Virtual Box
* Once you bootup, you will have CentOS instance that has Hadoop up and running
* We can use CLI, it also has browser interface
  * **Ambari** is available to easily navigate and manage different systems on Hadoop
  * Goto http://localhost:8888
* Launch Dashboard and login to Ambari
  * Username: maria_dev
  * Password: maria_dev
* #### Trouble shooting
  * Enable **virtualization** in your BIOS
  * Disable **Hyper-V acceleration** in Windows
