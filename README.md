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

#### 4. Run redis

- If you want to expose port to the host, specify `-p` parameter.

```
$ docker run -d --name redis -p 6379:6379 <your username>/redis
```

- If not, please use the following

```
$ docker run -d --name redis <your username>/redis
```

#### 5. Test redis server connection

- If you expose port to the host, you can directly connect to the redis server with cli

```
$ redis-cli
```

- If not, try to connect to the bash of your redis server

```
$ docker exec -it <your username>/redis /bin/bash
$ redis-cli
```