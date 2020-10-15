# Publish/Subscribe Pattern  
Enable an application to announce events to multiple interested consumers asynchronously, without coupling the senders to the receivers.

__Context and problem__  
In cloud-based and distributed applications, components of the system often need to provide information to other components as events happen.

Asynchronous messaging is an effective way to decouple senders from consumers, and avoid blocking the sender to wait for a response. However, using a dedicated message queue for each consumer does not effectively scale to many consumers. Also, some of the consumers might be interested in only a subset of the information. How can the sender announce events to all interested consumers without knowing their identities?  

__Solution__  
Introduce an asynchronous messaging subsystem that includes the following:  
* An input messaging channel used by the sender. The sender packages events into messages, using a known message format, and sends these messages via the input channel. The sender in this pattern is also called the publisher.  
* One output messaging channel per consumer. The consumers are known as subscribers.  
* A mechanism for copying each message from the input channel to the output channels for all subscribers interested in that message. This operation is typically handled by an intermediary such as a message broker or event bus.  

The following diagram shows the logical components of this pattern:  
![Publish Subscribe](./publish-subscribe.png)  

Pub/sub messaging has the following benefits:
* It decouples subsystems that still need to communicate. Subsystems can be managed independently, and messages can be properly managed even if one or more receivers are offline.  
* It increases scalability and improves responsiveness of the sender. The sender can quickly send a single message to the input channel, then return to its core processing responsibilities. The messaging infrastructure is responsible for ensuring messages are delivered to interested subscribers.  
* It improves reliability. Asynchronous messaging helps applications continue to run smoothly under increased loads and handle intermittent failures more effectively.  
* It allows for deferred or scheduled processing. Subscribers can wait to pick up messages until off-peak hours, or messages can be routed or processed according to a specific schedule.  
* It enables simpler integration between systems using different platforms, programming languages, or communication protocols, as well as between on-premises systems and applications running in the cloud.  
* It facilitates asynchronous workflows across an enterprise.  
* It improves testability. Channels can be monitored and messages can be inspected or logged as part of an overall integration test strategy.  
* It provides separation of concerns for your applications. Each application can focus on its core capabilities, while the messaging infrastructure handles everything required to reliably route messages to multiple consumers.  

## Prerequisites  
* Polling
* Streaming
* Persistent Storage

## Key Terms  
### Publish/Subscribe Pattern  
Often shortened as __Pub/Sub__, the Publish/Subscribe pattern is a popular messaging model that consists of __publishers__ and __subscribers__. Publishers publish messages to special __topics__ (sometimes called __channels__) without caring about or even knowing who will read those messages, and subscribers subscribe to topics and read messages coming through those topics.  

Pub/Sub systems often come with very powerful guarantees like __at-least-once delivery, persistent storage, ordering__ of messages, and __replayability__ of messages.  

### Idempotent Operation  
An operation that has the same ultimate outcome regardless of how many times it's performed. If an operation can be performed multiple times without charging its overall effect, it's idempotent. Operations performed through a __Pub/Sub__ messaging system typically have to be idempotent, since Pub/Sub systems tend to allow the same messages to be consumed multiple times.  

For example, increasing an integer value in a database is _not_ an idempotent operation, since repeating this operation will not have the same effect as if it had been performed only once. Conversly, setting a value to "COMPLETE" _is_ an idempotent operation, since repeating this operation will always yield the same result: the value will be "COMPLETE".  

### Apache Kafka ☆  
A distributed messaging system created by LinkedIn. Very useful when using the __streaming__ paradigm as opposed to __polling__.  
Website: [https://kafka.apache.org/](https://kafka.apache.org/)

### Cloud Pub/Sub ☆  
A highly-scalable Pub/Sub messaging service created by Google. Guarantees __at-least-once delivery__ of messages and supports "rewinding" in order to reprocess messages.  
Website: [https://cloud.google.com/pubsub/](https://cloud.google.com/pubsub/)