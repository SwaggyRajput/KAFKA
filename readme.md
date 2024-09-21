----------------------EVENT STREAMING----------------------
#Event streaming is the practice of capturing data in real-time from event sources like databases, sensors, mobile devices, cloud services, and software applications in the form of streams of events; storing these event streams durably for later retrieval; manipulating, processing, and reacting to the event streams in real-time as well as retrospectively; and routing the event streams to different destination technologies as needed. Event streaming thus ensures a continuous flow and interpretation of data so that the right information is at the right place, at the right time.


----------------------USE OF EVENT STREAMING----------------------
Event streaming is applied to a wide variety of use cases across a plethora of industries and organizations. Its many examples include:

#1.To process payments and financial transactions in real-time, such as in stock exchanges, banks, and insurances.
#2.To track and monitor cars, trucks, fleets, and shipments in real-time, such as in logistics and the automotive industry.
#4.To collect and immediately react to customer interactions and orders, such as in retail, the hotel and travel industry, and mobile APPS.
#5.To monitor patients in hospital care and predict changes in condition to ensure timely treatment in emergencies.
#6.To connect, store, and make available data produced by different divisions of a company.
#7.To serve as the foundation for data platforms, event-driven architectures, and microservices.


----------------------APACHE KAFKA----------------------
Apache Kafka® is an event streaming platform
Kafka combines three key capabilities so you can implement your use cases for event streaming end-to-end with a single battle-tested solution:

#To publish (write) and subscribe to (read) streams of events, including continuous import/export of your data from other systems.
#To store streams of events durably and reliably for as long as you want.
#To process streams of events as they occur or retrospectively.
#And all this functionality is provided in a distributed, highly scalable, elastic, fault-tolerant, and secure manner. Kafka can be deployed on bare-metal hardware, virtual machines, and containers, and on-premises as well as in the cloud. You can choose between self-managing your Kafka environments and using fully managed services offered by a variety of vendors.


--------------------------HOW DOES KAFKA WORK IN A NUTSHELL?------------------------------------------

Kafka is a distributed system consisting of servers and clients that communicate via a high-performance TCP network protocol. It can be deployed on bare-metal hardware, virtual machines, and containers in on-premise as well as cloud environments.

#Servers: Kafka is run as a cluster of one or more servers that can span multiple data centers or cloud regions. Some of these servers form the storage layer, called the brokers. Other servers run Kafka Connect to continuously import and export data as event streams to integrate Kafka with your existing systems such as relational databases as well as other Kafka clusters. To let you implement mission-critical use cases, a Kafka cluster is highly scalable and fault-tolerant: if any of its servers fails, the other servers will take over their work to ensure continuous operations without any data loss.

#Clients: They allow you to write distributed applications and microservices that read, write, and process streams of events in parallel, at scale, and in a fault-tolerant manner even in the case of network problems or machine failures. Kafka ships with some such clients included, which are augmented by dozens of clients provided by the Kafka community: clients are available for Java and Scala including the higher-level Kafka Streams library, for Go, Python, C/C++, and many other programming languages as well as REST APIs.

--------------------------EVENTS------------------------------------------
An event records the fact that "something happened" in the world or in your business. It is also called record or message in the documentation. When you read or write data to Kafka, you do this in the form of events. Conceptually, an event has a key, value, timestamp, and optional metadata headers. Here's an example event:

Event key: "Alice"
Event value: "Made a payment of $200 to Bob"
Event timestamp: "Jun. 25, 2020 at 2:06 p.m."

--------------------------PRODUCER AND CONSUMERS-------------------------------
#Producers are those client applications that publish (write) events to Kafka
#Consumers are those that subscribe to (read and process) these events.
#In Kafka, producers and consumers are fully decoupled and agnostic of each other, which is a key design element to achieve the high scalability that Kafka is known for.
#For example, producers never need to wait for consumers. Kafka provides various guarantees such as the ability to process events exactly-once.


--------------------------TOPICS-----------------------------------------

#Events are organized and durably stored in topics.
#A topic is similar to a folder in a filesystem, and the events are the files in that folder.An example topic name could be "payments".
#Topics in Kafka are always multi-producer and multi-subscriber: a topic can have zero, one, or many producers that write events to it, as well as zero, one, or many consumers that subscribe to these events.
#Events in a topic can be read as often as needed—unlike traditional messaging systems, events are not deleted after consumption.
#Instead, you define for how long Kafka should retain your events through a per-topic configuration setting, after which old events will be discarded. 
#Kafka's performance is effectively constant with respect to data size, so storing data for a long time is perfectly fine.

#Topics are partitioned, meaning a topic is spread over a number of "buckets" located on different Kafka brokers. This distributed placement of your data is very important for scalability because it allows client applications to both read and write the data from/to many brokers at the same time.
#When a new event is published to a topic, it is actually appended to one of the topic's partitions. Events with the same event key (e.g., a customer or vehicle ID) are written to the same partition, and Kafka guarantees that any consumer of a given topic-partition will always read that partition's events in exactly the same order as they were written.

--------------------------USE CASES-----------------------------------------
#1.Messaging
#2.Website Activity Tracking
#3.Metrics
#4.Log aggregation
#5.Stream Processing
#6.Event Sourcing
#7.Commit Log
