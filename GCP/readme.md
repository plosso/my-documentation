# PubSub

Core concepts

- Topic. A named resource to which messages are sent by publishers.
- Subscription. A named resource representing the stream of messages from a single, specific topic, to be delivered to the subscribing application. For more details about subscriptions and message delivery semantics, see the Subscriber Guide.
- Message. The combination of data and (optional) attributes that a publisher sends to a topic and is eventually delivered to subscribers.
- Message attribute. A key-value pair that a publisher can define for a message. For example, key iana.org/language_tag and value en could be added to messages to mark them as readable by an English-speaking subscriber.
- Publisher. An application that creates and sends messages to a single or multiple topics.
- Subscriber. An application with a subscription to a single or multiple topics to receive messages from it.
- Acknowledgment (or "ack"). A signal sent by a subscriber to Pub/Sub after it has received a message successfully. Acknowledged messages are removed from the subscription message queue.
- Push and pull. The two message delivery methods. A subscriber receives messages either by Pub/Sub pushing them to the subscriber chosen endpoint, or by the subscriber pulling them from the service.!

[Alt text](https://cloud.google.com/static/pubsub/images/pub_sub_flow.svg)