# Event Driven

```
curl --location 'http://localhost:8080/api/v1/orders' \
--header 'Content-Type: application/json' \
--data '{
    "name": "Apple Laptop",
    "qty": 1,
    "price": 1000
}'
```

# order-service

```logs
2024-01-15 18:51:07.377  INFO 19132 --- [nio-8080-exec-2] o.s.web.servlet.DispatcherServlet        : Initializing Servlet 'dispatcherServlet'
2024-01-15 18:51:07.389  INFO 19132 --- [nio-8080-exec-2] o.s.web.servlet.DispatcherServlet        : Completed initialization in 12 ms
2024-01-15 18:51:27.741  INFO 19132 --- [nio-8080-exec-3] n.j.orderservice.kafka.OrderProducer     : Order event => OrderEvent(message=order status is in pending state, status=PENDING, order=Order(orderId=c26a3c45-c189-4e75-9877-60dd723460cb, name=Apple Laptop, qty=1, price=1000.0))
2024-01-15 18:51:27.770  INFO 19132 --- [nio-8080-exec-3] o.a.k.clients.producer.ProducerConfig    : ProducerConfig values: 
```

# stock-service

```logs
2024-01-15 18:49:02.440  INFO 19122 --- [ntainer#0-0-C-1] org.apache.kafka.clients.NetworkClient   : [Consumer clientId=consumer-stock-1, groupId=stock] Node -1 disconnected.
2024-01-15 18:51:28.116  INFO 19122 --- [ntainer#0-0-C-1] n.j.stockservice.kafka.OrderConsumer     : Order event received in stock service => OrderEvent(message=order status is in pending state, status=PENDING, order=Order(orderId=c26a3c45-c189-4e75-9877-60dd723460cb, name=Apple Laptop, qty=1, price=1000.0))
```

# Email Service

```logs
2024-01-15 18:52:10.398  INFO 19612 --- [ntainer#0-0-C-1] n.j.emailservice.kafka.OrderConsumer     : Order event received in email service => OrderEvent(message=order status is in pending state, status=PENDING, order=Order(orderId=c26a3c45-c189-4e75-9877-60dd723460cb, name=Apple Laptop, qty=1, price=1000.0))
2024-01-15 19:01:10.518  INFO 19612 --- [ntainer#0-0-C-1] org.apache.kafka.clients.NetworkClient   : [Consumer clientId=consumer-email-1, groupId=email] Node -1 disconnected.
```
