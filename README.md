# Kafka Notes:

Official site: https://kafka.apache.org

Quick start guide: https://kafka.apache.org/quickstart

Download Kafka: https://www.apache.org/dyn/closer.cgi?path=/kafka/3.9.0/kafka_2.13-3.9.0.tgz
(This zip file contains all kafka tools and zookeeper tools)

# Apache Kafka's important core concepts or terminologies:
- Kafka cluster
- Kafka broker
- Kafka producer
- Kafka consumer
- Kafka topic
- Kafka partitions
- Kafka offsets
- Kafka consumer group

**********************************************************************************************

1. Kafka Cluster
A Kafka cluster is a distributed system made up of multiple Kafka brokers working together.
The cluster manages the distribution, storage, and replication of data across brokers for reliability and scalability.
Each Kafka cluster is identified by a unique cluster ID.

2. Kafka Broker
A Kafka broker is a server running Kafka.
It is responsible for handling requests from producers, consumers, and managing data storage for topics.
A broker manages partitions and ensures data replication across other brokers in the cluster.
3. Kafka Producer
A Kafka producer is a client that publishes messages to Kafka topics.
Producers can send messages to specific partitions of a topic (based on a key) or allow Kafka to distribute them evenly.
They handle retries, batching, and compression of data before sending.

4. Kafka Consumer
A Kafka consumer is a client that reads messages from Kafka topics.
Consumers subscribe to one or more topics and pull data in real-time or at their pace.
They use offsets to keep track of where to resume after processing messages.

5. Kafka Topic
A topic is a category or feed name where producers send records, and consumers read them.
Topics are split into partitions for scalability.
Kafka topics are immutable, meaning records cannot be updated after being written.

6. Kafka Partitions
A partition is a division of a topic to distribute data and workload across brokers.
Each partition is an ordered, immutable sequence of records.
Partitions allow Kafka to scale horizontally by spreading the load over multiple brokers.

7. Kafka Offsets
An offset is a unique identifier for each record within a partition.
It helps consumers track their position and ensures message delivery exactly once (or at least once).
Consumers can manually set the offset to replay or skip messages.

8. Kafka Consumer Group
A consumer group is a collection of consumers working together to consume messages from a topic.
Kafka distributes partitions among consumers in the group, ensuring no two consumers in the same group read the same partition.
Enables parallel processing and fault tolerance.

These concepts together make Kafka a powerful distributed event-streaming platform.

**********************************************************************************************

Important alwys Open CMD in kafka folder --> C:\kafka_2.13-3.9.0
# Run to start zookeeper server / service --> .\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties

Important alwys Open CMD in kafka folder --> C:\kafka_2.13-3.9.0
# Run to start kafka server --> .\bin\windows\kafka-server-start.bat .\config\server.properties


*********************************************************************************

NOTE:- Always start ZooKeeper service and Kafka broker service before running your spring boot application else you will get an exception.

STEP 1: DOWNLOAD AND INSTALL KAFKA
https://www.apache.org/dyn/closer.cgi?path=/kafka/3.9.0/kafka_2.13-3.9.0.tgz

STEP 2: START THE KAFKA ENVIRONMENT

# Start the ZooKeeper service
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties

# Start the Kafka broker service
.\bin\windows\kafka-server-start.bat .\config\server.properties

STEP 3: CREATE A TOPIC TO STORE YOUR EVENTS
.\bin\windows\kafka-topics.bat --create --topic topic_demo --bootstrap-server localhost:9092

STEP 4: WRITE SOME EVENTS INTO THE TOPIC
.\bin\windows\kafka-console-producer.bat --topic topic_demo --bootstrap-server localhost:9092

STEP 5:  READ THE EVENTS
.\bin\windows\kafka-console-consumer.bat --topic topic_demo --from-beginning --bootstrap-server localhost:9092
hello world
topic demo

STEP 6: TO LIST CREATED TOPICS
.\bin\windows\kafka-topics.bat --list --bootstrap-server localhost:9092

***************************************************************************************
