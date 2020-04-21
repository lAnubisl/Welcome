# Redis local setup

## Installation.

#### For MacOS
[https://webrewrite.com/how-to-install-redis-on-mac/](https://webrewrite.com/how-to-install-redis-on-mac/) or use in docker [https://hub.docker.com/_/redis](https://hub.docker.com/_/redis)

#### For Linux
[https://redis.io/download](https://redis.io/download) or use in docker [https://hub.docker.com/_/redis](https://hub.docker.com/_/redis)

#### For Windows
Redis is not windows friendly. You can try any option from this thread: [https://stackoverflow.com/questions/6476945/how-do-i-run-redis-on-windows](https://stackoverflow.com/questions/6476945/how-do-i-run-redis-on-windows) or use redis in docker [https://hub.docker.com/_/redis](https://hub.docker.com/_/redis)

## Configuration.
When Redis is up and running it does not require additional configuration for OpenMAVN projects. All you need is to build connection string which should look like this: [server_address]:[server_port],password=[password],ssl=False,abortConnect=False
and put it into the service setting file.
