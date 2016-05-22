Docker Redis
--

Step by step to create your redis docker image and start it by exposing 6379 port.

#### 1. Create Docekrfile

```
$ mkdir redis && touch Dockerfile
```

#### 2. Create Redis Dockerfile

```
FROM        ubuntu:14.04
RUN         apt-get update && apt-get install -y redis-server
EXPOSE      6379
ENTRYPOINT  ["/usr/bin/redis-server"]
```

#### 3. Build redis images

```
$ docker build -t <your username>/redis .
```

#### 4. Run redis with expose 6379 port

```
$ docker run -d --name redis -p 6379:6379 dockerfile/redis
```

#### 5. Test redis server connection

```
$ redis-cli
```