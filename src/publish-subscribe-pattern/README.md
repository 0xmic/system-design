# Publish/Subscribe Pattern


## Prerequisites  
* Polling
* Streaming
* Persistent Storage

## Key Terms  
### Publish/Subscribe Pattern  
Often shortened as __Pub/Sub__, the Publish/Subscribe pattern is a popular messaging model that consists of __publishers__ and __subscribers__. Publishers publish messages to special __topics__ (sometimes called __channels__) without caring about or even knowing who will read those messages, and subscribers subscribe to topics and read messages coming through those topics.  

Pub/Sub systems often come with very powerful guarantees like __at-least-once delivery, persistent storage, ordering__ or messages, and __replayability__ of messages.  

### Idempotent Operation  
An operation that has the same ultimate outcome regardless of how many times it's performed. If an operation can be performed multiple times without charging its overall effect, it's idempotent. Operations performed through a __Pub/Sub__ messaging system typically have to be idempotent, since Pub/Sub systems tend to allow the same messages to be consumed multiple times.  

For example, increasing an integer value in a database is _not_ an idempotent operation, since repeating this operation will not have the same effect as if it had been performed only once. Concersly, setting a value to "COMPLETE" _is_ an idempotent operation, since repeating this operation will always yield the same result: the value will be "COMPLETE".  

### Apache Kafka ☆  
A distributed messaging system created by LinkedIn. Very useful when using the __streaming__ paradigm as opposed to __polling__.  
Website: [https://kafka.apache.org/](https://kafka.apache.org/)

### Cloud Pub/Sub ☆  
A highly-scalable Pub/Sub messaging service created by Google. Guarantees __at-least-once delivery__ of messages and supports "rewinding" in order to reprocess messages.  
Website: [https://cloud.google.com/pubsub/](https://cloud.google.com/pubsub/)