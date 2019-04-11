
#### Links

``$ docker run -dit  -p 6379:6379 -v /data/redis/redis.conf:/usr/local/etc/redis/redis.conf --name myredis redis redis-server /usr/local/etc/redis/redis.conf``

docker-compose.yml

```
version: '2'
services:
  redis:
    container_name: my-redis
    image: redis
    # command: redis-server /usr/local/etc/redis/redis.conf
    restart: unless-stopped
    # appendonly: yes
    # maxmemory: 5012
    volumes:
      - ./:/data
      #- ./redis.conf:/usr/local/etc/redis/redis.conf
    ports:
      - "0.0.0.0:6379:6379"
```

[Start containers automatically](https://docs.docker.com/config/containers/start-containers-automatically/)

[Ensuring Containers Are Always Running with Docker’s Restart Policy](https://blog.codeship.com/ensuring-containers-are-always-running-with-dockers-restart-policy/)

[Setting up a Redis test environment using Docker Compose](https://cheesyprogrammer.com/2018/01/04/setting-up-a-redis-test-environment-using-docker-compose/)

[Redis Persistence](https://redis.io/topics/persistence)
