# RabbitMQ local setup

## **Installation.**
Follow these installation instructions: [https://www.rabbitmq.com/download.html](https://www.rabbitmq.com/download.html)

## Configuration.
When RabbitMQ is up and running it does not require additional configuration for OpenMAVN projects. All you need is to build connection string which should look like this: amqp://[user_login]:[user_password]@[server_address]:[server_port]
and put it into the service setting file.