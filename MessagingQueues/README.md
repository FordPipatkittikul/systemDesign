# 1 Messaging Queues

A messaging queue is a form of asynchronous communication where messages are stored in a queue and processed independently by consumers. It helps decouple different parts of a system, allowing them to communicate without waiting for an immediate response.

How It Works

1. Producer – Sends messages to the queue.

2. Message Queue – Temporarily holds messages until they are processed.

3. Consumer – Retrieves and processes messages from the queue.

This setup ensures asynchronous processing, meaning the producer can continue its work without waiting for the consumer to finish processing.

# 1.1 Patterns

- Point-to-Point (Work Queue) – One producer, one consumer per message (e.g., task processing).

- Publish-Subscribe (Pub/Sub) – One producer, multiple consumers receive the same message (e.g., event notifications).

# 1.2 Benefits

- Asynchronous Processing – Tasks can be processed later without blocking the main system.
- Scalability – Multiple consumers can process messages in parallel.
- Fault Tolerance – Messages remain in the queue until processed, preventing data loss.
- Decoupling – Services communicate via messages without depending on each other’s availability.
- Load Balancing – Distributes workload across multiple consumers efficiently.

# 1.3 Popular Message Queue Systems

# 1.3.1 RabbitMQ

- Type: Message Broker (Traditional Message Queue)
- Best For: Reliable message delivery, request-response patterns, distributed workloads
- Protocol: AMQP (Advanced Message Queuing Protocol)

How it works

RabbitMQ follows the **producer-consumer model**, using **exchanges and queues** to route messages. It ensures reliable message delivery using acknowledgments, retries, and dead-letter queues.

1. Producer or Publisher – Sends a message to an exchange.
2. Exchange – Determines how messages are routed to queues (direct, fanout, topic, headers).
3. Queue – Stores messages until a consumer processes them.
4. Consumer – Listens to a queue and processes messages asynchronously.
5. Acknowledgment & Redelivery – If a consumer fails to process a message, RabbitMQ can redeliver it.

![alt text](<Screenshot (59).png>)

Concept

Routing keys: it is represent the address of the queue it needs to go to.

RabbitMQ Routing Mechanisms

- Direct Exchange – Routes messages based on exact matching keys.
![alt text](<Screenshot (60).png>)

- Fanout Exchange – Broadcasts messages to all queues.
![alt text](<Screenshot (61).png>)

- Topic Exchange – Routes messages using wildcard matching (e.g., log.error).
![alt text](<Screenshot (62).png>)

- Headers Exchange – Routes messages based on message headers instead of routing keys.
![alt text](<Screenshot (63).png>)


source: https://www.javainuse.com/messaging/rabbitmq/exchange

# 1.3.2 Kafka

- Type: Distributed Event Streaming Platform
- Best For: High-throughput event processing, real-time analytics, event sourcing
- Protocol: Custom TCP-based

How it works

In kafka terms, **queue is called topic** and **messages are called events**

Kafka is a log-based distributed messaging system. It is optimized for high throughput and is commonly used in event-driven architectures.

1. Producer – Writes messages to a topic (instead of a queue).
2. Topic & Partitions – Messages are distributed across partitions for scalability.
3. Broker – Kafka servers that store and manage topics and partitions.
4. Consumer Group – Multiple consumers can subscribe to topics and read messages in parallel.
5. Offsets – Kafka tracks messages using offsets, allowing consumers to replay messages if needed.

Kafka Topics & Partitions

- Topics – Categories that messages belong to.
- Partitions – Kafka splits topics into partitions for parallel processing.