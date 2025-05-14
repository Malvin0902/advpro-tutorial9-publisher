## a. How much data does the publisher send in one run?

The amount of data sent by the publisher program in one run depends on how the program is written. If the program sends, for example, 100 messages and each message is 1 KB in size, then it sends **100 KB of data**.
To know the exact amount, you need to:

* Check how many messages are sent.
* Check the size of each message.

For example:

```python
message = "Hello, World!"  # 13 bytes
for i in range(100):
    channel.basic_publish(..., body=message)
```

This would send **13 bytes × 100 = 1,300 bytes (or 1.3 KB)** in total.

---

## b. What does it mean if the URL `amqp://guest:guest@localhost:5672` is the same in the subscriber program?

If both the **publisher** and **subscriber** use the same URL `amqp://guest:guest@localhost:5672`, it means they are **connecting to the same RabbitMQ server** running on the local machine (`localhost`), using the same username and password (`guest:guest`), and the default AMQP port (`5672`).

This allows the publisher to send messages to the broker, and the subscriber to receive them from the same broker — they are both working with the **same message system**.
