# Commands
Start Zookeper Container and expose PORT 2181.
```
docker run -p 2181:2181 zookeeper
```

Start Kafka Container, expose PORT 9092 and setup ENV variables.

To Find your local IP address run this CMD `` ipconfig ``

**Ubuntu** command:
```
docker run -p 9092:9092 \
-e KAFKA_ZOOKEEPER_CONNECT=<PRIVATE_IP>:2181 \
-e KAFKA_ADVERTISED_LISTENERS=PLAINTEXT://<PRIVATE_IP>:9092 \
-e KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR=1 \
confluentinc/cp-kafka
```

**Windows** command:
```
docker run -p 9092:9092 ^
-e KAFKA_ZOOKEEPER_CONNECT=<PRIVATE_IP>:2181 ^
-e KAFKA_ADVERTISED_LISTENERS=PLAINTEXT://<PRIVATE_IP>:9092 ^
-e KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR=1 ^
confluentinc/cp-kafka
```
## Running Locally

### To check the kafka is working or not
```
node admin.js
```

### Test case - one

Run Multiple Consumers 
```
node consumer.js <GROUP_NAME>
```
Ex: `` node consumer.js group-1 `` `` node consumer.js group-1 `` `` node consumer.js group-2 ``

Create Producer
```
node producer.js
```
```
> Saikiran south
> Saikiran north
```
partitions are hapening basis on the ``south north``

