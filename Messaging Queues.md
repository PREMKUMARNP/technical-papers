# Messaging Queues

## What are Messaging Queues?

When I started reading about this topic, the easiest way I found to understand it was to think of a queue at a ticket counter. People join the line and get served one by one. A messaging queue works in a similar way for software. One program sends a message and it waits in a queue until another program is ready to pick it up. The program that sends the message is called the producer, and the program that reads it is called the consumer. The software in the middle that manages the queue is called a message broker.

## Why are they used?

Without a queue, two programs have to talk to each other directly, and both need to be running at the same time. With a queue, the sender can drop the message and carry on with its work. Some of the main reasons people use queues are:

* The sender and receiver do not depend on each other, so one can be restarted or updated without breaking the other.
* If the receiver is down, the messages are not lost. They wait in the queue.
* If a lot of requests come at the same time, the queue holds them and the receiver handles them at its own speed.
* Slow jobs like sending emails can be done in the background, so the user does not have to wait.

## What are popular tools?

Some tools that are used a lot are listed below.

1. RabbitMQ is a free and open-source broker. It is a good one for beginners.
2. Apache Kafka is built to handle a very large amount of data and live data streams.
3. Amazon SQS is a queue service from AWS that is run by Amazon, so we do not need to manage any servers.
4. Azure Service Bus is a similar service from Microsoft.
5. Apache ActiveMQ is an open-source broker that is often used with Java.

## What is an Enterprise Message Bus?

An Enterprise Message Bus is a common pathway that connects many applications inside a company. Without it, every application would need its own connection to every other application, and this becomes messy when there are many systems. With a message bus, each application connects only to the bus. The bus then takes care of delivering the message to the right place. It can also change the format of a message so that different systems can understand it.

For example, if a shopping company has separate systems for orders, billing and stock, the order system can send one message to the bus. The billing and stock systems then both receive it from there.

A queue usually connects one sender to one receiver, while a message bus connects many systems together.

## Conclusion

Messaging queues help programs share data without waiting for each other, and they make a system more reliable and easier to grow. RabbitMQ, Kafka and Amazon SQS are some common tools for this. An Enterprise Message Bus uses the same idea on a bigger scale to connect all the applications in a company.

## References

* [What is Message Queuing - AWS](https://aws.amazon.com/message-queue/)
* [RabbitMQ Documentation](https://www.rabbitmq.com/docs)
* [Apache Kafka Documentation](https://kafka.apache.org/documentation/)
* [Amazon SQS Developer Guide](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html)
* [Azure Service Bus Overview - Microsoft Learn](https://learn.microsoft.com/en-us/azure/service-bus-messaging/service-bus-messaging-overview)
* [Message Bus Pattern - Enterprise Integration Patterns](https://www.enterpriseintegrationpatterns.com/patterns/messaging/MessageBus.html)
