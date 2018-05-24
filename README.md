# kotlin-ktor-kafka

This is a simple ktor web application, backed by Kafka Streams interactive queries. To run locally:

- Start zookeeper: bin/zookeeper-server-start.sh config/zookeeper.properties
- Start kafka server: bin/kafka-server-start.sh config/server.properties
- Create topic: bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic streams-plaintext-input
- Start app
- Produce events: bin/kafka-console-producer.sh --broker-list localhost:9092 --topic streams-plaintext-input
- Hit endpoint: curl localhost:8080/word/{word}
