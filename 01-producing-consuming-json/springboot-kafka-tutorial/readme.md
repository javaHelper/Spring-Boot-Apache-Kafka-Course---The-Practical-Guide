#

http://localhost:8080/api/v1/kafka/publish?message=hello%20world

```logs
2024-01-15 17:52:23.206  INFO 17355 --- [ntainer#0-0-C-1] n.j.springboot.kafka.JsonKafkaConsumer   : Json message received -> User(id=0, firstName=null, lastName=null, email=null)
2024-01-15 17:53:13.679  INFO 17355 --- [nio-8080-exec-3] n.j.springboot.kafka.JsonKafkaProducer   : Message sent -> User(id=1, firstName=John, lastName=Doe, email=john.doe@gmail.com)
2024-01-15 17:53:13.742  INFO 17355 --- [ntainer#0-0-C-1] n.j.springboot.kafka.JsonKafkaConsumer   : Json message received -> User(id=1, firstName=John, lastName=Doe, email=john.doe@gmail.com)
```
