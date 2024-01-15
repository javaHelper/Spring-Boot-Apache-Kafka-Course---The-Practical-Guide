# 


Recursively Remove .DS_Store
- Open up Terminal
- In the command line, cd to/your/directory
- Finally, in the command line, type: `find . -name '.DS_Store' -type f -delete`. Press enter.

STEP 1: GET KAFKA
Download the latest Kafka release and extract it:

```sh
$ tar -xzf kafka_2.13-3.6.1.tgz
$ cd kafka_2.13-3.6.1
```

# Start the ZooKeeper service

```
bin/zookeeper-server-start.sh config/zookeeper.properties
```

# Start the Kafka broker service
```
bin/kafka-server-start.sh config/server.properties
```
