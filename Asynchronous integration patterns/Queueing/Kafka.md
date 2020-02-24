# Kafka Connector

This standard library provides the Jolie programmer with the capability within a single microservice to produce and consume messages to and from several Kafka topics.

## Kafka Producer

The Jolie Kafka connector does not need to instantiate explicitly a producer, this allows the programmer to send simple or complex messages to any topic. In the following example, we are collecting the search activities carried out by users of an e-commerce site 


```jolie
    [ searchProduct ( request )( response ){
        //... some code to generate the token
        with(req){
            .broker="localhost:9092";
            .clientId="searchProduct";
            .topic="query";
            .payload.key = request.token;
            .payload.value << request.query
        }
        sendMessageToTopic@Kafka(req)()
    }
```
Likewise, there is no explicit declaration of the serializer object this is given by the fact that the connector will analyse the content of the nodes payload.key payload.value and instantiate the correct serialization artefact.
If at any point in the code the user will try to use a different type of value or key for the same topic this will provoke and exception.

## Kafka Consumer

The Jolie Kafka connector allows the developer to instantiate multiple consumers that will push the message(s) to a developer selected operation. The operation can be either RequestResponse if we want to achieve synchronous processing of the Kafka topic content, or Oneway if we want to have continuos asynchronous flux of messages from the topic.

```jolie
type ConsumerInRequest{
    .payload*:void{
        .offset:long
        .key:undefined
        .value:undefined
    }    
}

type ConsumerErrorMessage{
      .offset:long    
}

interface consumerInterface{
  RequestResponse:
  processSyncronous(ConsumerInRequest)(void) throws ErrorProcess (ConsumerErrorMessage)
  OneWay:
  processAsynchronous(ConsumerInRequest)
}

init{
     with(req){
        .broker="localhost:9092";
        .operation = "processSyncronous"
        .autocommit= false;
        .groupId="ProcessingGroup";
        .topic="query";
        .keyType = "string";
        .valueType = "value";
        .duration = 10L
    }

    setConsumer@Kafka(req)
    
    undef(req)
    with(req){
        .broker="localhost:9092";
        .operation = "processAsynchronous"
        .autocommit= true;
        .groupId="ProcessingGroup1";
        .topic="query"
        .keyType = "string";
        .valueType = "value";
        .duration = 10L
    }

    setConsumer@Kafka(req)

}
```

If we want to set RequestResponse processing operation we need to set the node .autocommit= false to signal to the Kafka that will be up to the operation signal the commit on the consumer. The implementation of this process has been constructed to require only in case of an error the explicit indication of the first not correctly processed message. The name of the fault is irrelevant but the returning type needs to be ConsumerErrorMessage.
On the other hand, if we want to set a OneWay processing operation we to set the node .autocommit= true to signal to the Kafka that will be up to  the consumer itself to commit the changes
The wrong combination of .autocommit and Operation type will result in an exception raised by the setConsumer operation 





