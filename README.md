# First Question
> How many data your publlsher program will send to the message broker in onerun? <br>
- The program will execute five data points. Each `publish_event` call sends one message, with IDs ranging from 1 to 5, corresponding to messages from Amir, Budi, Cica, Dira, and Emir.<br>
> The url of: ```amqp://guest:guest@localhost:5672``` is the same as in the subscriber program, what does it mean?<br>
- The same URL being used in both the publisher and subscriber indicates that both components are connecting to the same RabbitMQ server instance to send and receive messages. This is common in event-driven architectures where multiple services interact through a messaging system like RabbitMQ. By connecting to the same server and channel, the publisher can publish messages that the subscriber can listen and process.

# RUNNING RABIT MQ
![rabbitmq1.png](image/rabbitmq1.png)

# SENDING AND PROCESSING EVENT
![](image/log1.png)
When I run the subscriber first (cargo run in the subscriber directory), it starts listening for messages on the user_created queue. Running the publisher next (cargo run in the publisher directory) sends messages to the queue. Since the subscriber is already listening, it immediately receives these messages as they arrive and handles them using the UserCreatedHandler. The handler's handle function is invoked for each message, printing a confirmation that it has been received along with the message details.

This is basically demonstrates a functional message queue system where messages can be asynchronously sent by a publisher and received by a subscriber. All of this managed through a messaging protocol (AMQP) and handled according to custom logic defined in Rust.
