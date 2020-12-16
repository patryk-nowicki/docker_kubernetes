# Docker Kubernetes


## simpleweb: 

To run containers with mapped ports:

```bash
docker build .
docker run -p 8080:8080 <image_hash>
```

To start app go to: ``localhost:8080`` or `127.0.0.1:8080`

## visits-completed:
 
To run containers with docker compose 

```bash
docker-compose up
```

ports are mapped in dockerfile.yml

```bash
version: "3"
services:
  redis-server:
    image: "redis"
  node-app:
    restart: on-failure
    build: .
    ports:
      - "4001:8081"
```

To start app go to: ``localhost:4001`` or `127.0.0.1:4001`


Docker is creating 2 services : 
  1) redis-server (with default client 127.0.0.1:6379 for storing keys) 
  2) node-app: (image built on Dockerfile specs. where npm is started)
 
See index.js to take a look on node-app and server communication. 

### redis-cli comands
Below there are some commands for redis-cli. 
It can be used for redis server and user communication. 

To start shell/bash conrtainer command prompt 

```bash
docker exec -it <image_hash> sh 
```
By defualt cmd sturtup in placed in data folder so bin/bash won't work (use bash instead)
```bash
docker exec -it <image_hash> bash
```

`redis-cli` commands 

to get help
```bash
  redis-cli --help
```

scan keys 
```bash
redis-cli --scan
```

get value of the key 
```bash
redis-cli get visits 
```

setting key values to 0
```bash
redis-cli set visits 0
```
TODO: 
* Add docker image alias in place of <image_hash>
