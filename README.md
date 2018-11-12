# Splunk Workshop
## Introduction -- vipul

## Why Splunk? -- Saivarun 

## Using Splunk Interface -- Krishnaveni

### Show how to use search in splunk
### show how to import data static files into splunk
### show how to visualize data and create dashboards

## Splunk-Kafka-Connector
> Clone this repo before you start working!!
### 1. Download Splunk Connector for kafka
By Following the link below download the executable jar file [Download](https://github.com/splunk/kafka-connect-splunk/releases)
![Download](/images/kafka-connect-splunk.PNG)
> Make sure that you place the jar file in `Splunk-Kafka-Connector/kafka_2.11-2.0.0/bin/windows/`
> we will use this path later to start our kafka connector
### 2. Start Zoopkeeper
> Please make sure that your current working directory is Splunk-Kafka-Connector

Start the Zoopkeeper using the following command `kafka_2.11-2.0.0/bin/windows/zookeeper-server-start.bat zookeeper.properties`
> You can also double click on the `zookeeper-server-start.bat` file
### 3. Start Kafka Server
> Please make sure that your current working directory is Splunk-Kafka-Connector

Start the kafka server using the following command `kafka_2.11-2.0.0/bin/windows/kafka-server-start.bat server.properties`
> You can also double click on the `kafka-server-start.bat` file
### 4. Create a topic in kafka
> Please make sure that your current working directory is Splunk-Kafka-Connector

Create a topic on the previous server using the following command `kafka_2.11-2.0.0/bin/windows/kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic bearcat_messages`
> You can also double click on the `kafka-topics.bat` file
### 5. Start a console Producer
> Please make sure that your current working directory is Splunk-Kafka-Connector

Start a console producer to write to the kafka topic we created earlier using the following command `kafka_2.11-2.0.0/bin/windows/kafka-console-producer.bat --broker-list localhost:9092 --topic bearcat_messages`
> You can also double click on the `kafka-console-producer.bat` file
### 6. Start a console Customer
> Please make sure that your current working directory is Splunk-Kafka-Connector

Start a console consumer to read from the kafka topic we created earlier using the following command `kafka_2.11-2.0.0/bin/windows/kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic bearcat_messages --from-beginning`
> You can also double click on the `kafka-console-consumer.bat` file
### 7. Create Connection Splunk-Kafka
> Please make sure that your current working directory is Splunk-Kafka-Connector

Start a console consumer to read from the kafka topic we created earlier using the following command `kafka_2.11-2.0.0\bin\windows\connect-distributed.bat kafka_2.11-2.0.0\config\connect-distributed.properties`
> You can also double click on the `connect-distributed.bat` file
### 8. verifying Sink Connector
#### 1. Postman
* Make a `GET` Request to the Kafka Connector API Service and verify that you have started in step 7 using the URI `http://localhost:8083/connector-plugins/` and verify that you must have an entry for `com.splunk.kafka.connect.SplunkSinkConnector`
* You can refer to the below screenshot for more details.
![verifySink](/images/verifySink.png)

#### 2. CURL
* Use the following command to make a `GET` request using CURL 
> curl http://localhost:8083/connector-plugins/ and verify that you must have an entry for `com.splunk.kafka.connect.SplunkSinkConnector`
* You can refer to the below screenshot for more details.
![verifySink](/images/curlverifySink.png)

## References
* https://github.com/splunk/kafka-connect-splunk/
* https://docs.confluent.io/current/connect/userguide.html#id3
* https://docs.confluent.io/current/connect/references/restapi.html
* https://kafka.apache.org/intro


## Contact
- Vipul chandoor
- Saivarun Illendula
- Krishnaveni Karri
- Santhosh Bonala