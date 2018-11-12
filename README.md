# Splunk Workshop
## Introduction

## Why Splunk?

## Using Splunk Interface

## Splunk-Kafka-Connector
> Clone this repo before you start working!!
### Download Splunk Connector for kafka
By Following the link below download the executable jar file [Download](https://github.com/splunk/kafka-connect-splunk/releases)
![Download](./images/kafka-connect-splunk)
> Make sure that you place the jar file in `h07/kafka_2.11-2.0.0/bin/windows/`
> we will use this path later to start our kafka connector
### Start Zoopkeeper
> Please make sure that your current working directory is Splunk-Kafka-Connector

Start the Zoopkeeper using the following command `kafka_2.11-2.0.0\bin\windows\zookeeper-server-start.bat zookeeper.properties`
> You can also double click on the `zookeeper-server-start.bat` file
### Start Kafka Server
> Please make sure that your current working directory is Splunk-Kafka-Connector

Start the kafka server using the following command `kafka_2.11-2.0.0\bin\windows\kafka-server-start.bat server.properties`
> You can also double click on the `kafka-server-start.bat` file
### Create a topic in kafka
> Please make sure that your current working directory is Splunk-Kafka-Connector

Create a topic on the previous server using the following command `kafka_2.11-2.0.0\bin\windows\kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic bearcat_messages`
> You can also double click on the `kafka-topics.bat` file
### Start a console Producer
> Please make sure that your current working directory is Splunk-Kafka-Connector

Start a console producer to write to the kafka topic we created earlier using the following command `kafka_2.11-2.0.0\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic bearcat_messages`
> You can also double click on the `kafka-console-producer.bat` file
### Start a console Customer
> Please make sure that your current working directory is Splunk-Kafka-Connector
Start a console consumer to read from the kafka topic we created earlier using the following command `kafka_2.11-2.0.0\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic bearcat_messages --from-beginning`
> You can also double click on the `kafka-console-consumer.bat` file

### create Connection Splunk-Kafka
## Resources

## Contact
- Vipul chandoor
- Saivarun Illendula
- Krishnaveni Karri
- Santhosh Bonala