# Docker Kubernetes


> simpleweb: 

```bash {cmd}
docker build .
docker run -p 8080:8080 <image_hash>
```
volumes -v /x:x/y/x



visits-completed:
 
``` 
docker-compose up
```
creating 2 services: 
  * redis-server -  with (default) client 127.0.0.1:6379 where visits key is stored 
  * node-app (see: index.js) 
 
some commands for redis-cli (defualt sturtup in data folder)
docker exec -it <image_hash> sh 
docker exec -it <image_hash> bash


`redis-cli` commands 
```
  redis-cli --help
```

```
redis-cli --scan
```

```
redis-cli get visits 
```
to restart visits :D 
  redis-cli set visits 0


```bash {cmd}
ls .
```

```bash {cmd=true}
ls .
```

```javascript {cmd="node"}
const date = Date.now()
console.log(date.toString())
```


