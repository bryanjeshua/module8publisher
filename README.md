# First Question
> How many data your publlsher program will send to the message broker in onerun? <br>
- The program will execute five data points, where each `publish_event` call sends one message, with IDs ranging from 1 to 5, corresponding to messages from Amir, Budi, Cica, Dira, and Emir.<br>
> The url of: ```amqp://guest:guest@localhost:5672``` is the same as in the subscriber program, what does it mean?<br>
- The same URL being used in both the publisher and subscriber indicates that both components are connecting to the same RabbitMQ server instance to send and receive messages. This is common in event-driven architectures where multiple services interact through a messaging system like RabbitMQ. By connecting to the same server and channel, the publisher can publish messages that the subscriber can listen and process.