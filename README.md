sysbench-mongodb
================

Sysbench for MongoDB and Percona Server for MongoDB


Requirements
=====================

* Java 1.8
* The MongoDB Java driver must exist and be in the CLASSPATH, as in "export CLASSPATH=/home/tcallaghan/java_goodies/mongo-2.13.0.jar:.". If you don't already have the MongoDB Java driver, then execute the following two commands:
    * wget https://oss.sonatype.org/content/repositories/releases/org/mongodb/mongo-java-driver/3.2.1/mongo-java-driver-3.2.1.jar
    * export CLASSPATH=$PWD/mongo-java-driver-3.2.1.jar:$CLASSPATH
* This example assumes that you already have a MongoDB or Percona Server for MongoDB server running on the same machine as the Sysbench client application.
* You can connect a different server or port by editing the config.bash script.


Running the benchmark
=====================

In the default configuration the benchmark creates 16 collections, each with 10 million documents. You may want to watch the size of the database relative to your memory size to ensure you are testing just a memory based workload vs a workload that is exceeding memory and utilizing disk as well. All options are configurable in config.bash (or custom config file with the same options)

To run:

```bash
git clone https://github.com/Percona-Lab/sysbench-mongodb.git
cd sysbench-mongodb

```

Edit config.bash to match your environment. You will most likely want to change the server/port and credentials for your database.

```bash
./run.simple.bash

```

If you want to have multiple config files you can simply copy config.bash and specify the config you would like on the command line:

```bash
./run.simple.bash my_custom_config.bash

```
