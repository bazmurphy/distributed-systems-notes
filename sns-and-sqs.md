# AWS SNS and SQS

## Simple Notification Service

![](/images/aws-sns.png)

As one of the earliest managed services launched on AWS, `SNS` is a distributed `publish`/`subscribe` solution used for `application-to-application` (A2A) and `application-to-person` (A2P) communication.

`SNS` `topics` are used to enable communication:

- `producers` publish messages to `topics`,
- and `consumers` `subscribe` to these `topics` to receive `messages`.

- You can deliver `messages` to various types of `subscribers`,
  - such as AWS SQS queues, AWS Lambda functions, and HTTP endpoints.
- You can also use SNS to send SMS messages, email, and push notifications to end-user devices.

There are two types of topics:

1. `Standard` `topics`.

- They offer maximum throughput, best-effort ordering, and best-effort deduplication (messages may be delivered more than once).

2. `FIFO` `topics`.

- Provide strict ordering and deduplication. The downside is that you can use FIFO topics to send events only to SQS queues (no other type of consumer is supported).

## Simple Queue Service

![](/images/aws-sqs.png)

AWS `SQS` is a distributed, managed `queueing` `service` used for communication between applications, microservices, and distributed systems.

As with most messaging middleware, SQS consists of three major components:

- `Producers` (components that send messages to the queue).

- `Queue` (which stores messages).

- `Consumers` (other components that receive messages from the queue).

There are two types of queues:

- `Standard` `queues`. They offer maximum throughput, best-effort ordering, and at-least-once delivery.

- `FIFO` `queues`. Designed to guarantee that messages are processed exactly once, in the same order that they are sent.

---

## Key distinctions between SNS and SQS:

- `SNS` supports A2A and A2P communication, while `SQS` supports only A2A communication.

- `SNS` is a pub/sub system, while `SQS` is a queueing system. You'd typically use `SNS` to send the same `message` to multiple `consumers` via `topics`. In comparison, in most scenarios, each `message` in an `SQS` `queue` is processed by only one `consumer`.

- With `SQS`, messages are delivered through a long polling `pull mechanism`, while `SNS` uses a `push mechanism` to immediately deliver `messages` to subscribed endpoints.

- `SNS` is typically used for applications that need realtime notifications, while `SQS` is more suited for message processing use cases.

- `SNS` does not persist messages - it delivers them to subscribers that are present, and then deletes them. In comparison, `SQS` can persist messages (from 1 minute to 14 days).

## When to use AWS SNS

- Sending email, SMS, and push notifications to end-users in realtime. Note that you can send push notifications to Apple, Google, Fire OS, and Windows devices.

- Broadcasting messages to multiple subscribers (for example, fanning out the same push notifications to all users of your app).

- Workflow systems. For example, you can use SNS to pass events between distributed apps, or to update records in various business systems (e.g., inventory changes).

- Realtime alerts and monitoring applications.

## When to use AWS SQS

- Asynchronous processing workflows.

- Processing messages in parallel (by using multiple SQS queues).

- Decoupling and scaling microservices, distributed systems, and serverless applications.

- Sending, storing, and receiving events with reliable messaging guarantees (ordering & exactly-once processing).

## Why use AWS SNS and SQS together?

While both AWS `SNS` and `SQS` are useful on their own, they can also be combined to create a more robust and reliable system.

For example, by using `SNS` and `SQS` together, messages can be delivered to applications that require immediate notification of an event, and also persisted in an `SQS` queue for other applications to process at a later time.

You can also combine `SNS` and `SQS` to ensure end-to-end message ordering.

For example, you can have an `SNS` topic that delivers messages to subscribed `SQS` FIFO queues in the exact order that the messages are published to the topic. The `SQS` FIFO queues' consumer(s) receive the messages in the same order they are sent to the queue.

Finally, `SQS` works nicely with `SNS` in a fanout pattern, where you want to send identical copies of a message to multiple queues in parallel.

![](/images/aws-sns-sqs.png)

---

`SNS` is a `pub`/`sub` system primarily used for `application-to-application` (A2A) communication. SNS does support application-to-person (A2P) communication as well. Still, there are some limitations: email, SMS and push notifications are the only ways in which messages can reach end-user devices, and you have no guarantees they will be delivered in order or exactly-once.

`SQS` is a message queuing system that enables you to decouple and scale microservices, distributed systems, and serverless applications.

---
