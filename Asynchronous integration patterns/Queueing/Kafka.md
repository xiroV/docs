# Kafka Connector

This standard library provides the Jolie programmer with the capability within a single microservice to produce and consume messages to and from several Kafka topics.

## Kafka Producer

The Jolie Kafka connector does not need to instantiate explicitly a producer, this allows the programmer to send simple or complex messages to any topic at any point of the code like in the example

```jolie
    [ setQuotation ( request )( response ){
        with(req){
            .broker="localhost:9092";
            .clientId="client1";
            .topic="MBTE";
            .payload.key = token;
            .payload.value.stockCode="FCA";
            .payload.value.price = 20.0
        }
        sendMessageToTopic@Kafka(req)()
    }
```
Likewise, there is no explicit declaration of the serializer object this is given by the fact that the connector will analyse the content of the nodes payload.key payload.value and instantiate the correct serialization artefact.
If at any point in the code the user will try to use a different type of value or key for the same topic this will provoke and exception.

## Kafka Consumer

The Jolie Kafka connector allows the developer to  inst





