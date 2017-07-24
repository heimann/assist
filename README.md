# assist

# docker

## Bash into docker container
```
docker run -ti --entrypoint=sh <container>
```

## Remove all docker containers created today
```
docker ps -a | grep -v 'days' | grep -v 'CONTAINER' | awk '{print $1}' | xargs --no-run-if-empty docker rm && docker ps -a
```

## Remove all docker volumes
```
docker volume ls | awk '{print $2}' | xargs docker volume rm
```

## Remove all docker images
```
docker images | awk '{print $3}' | xargs docker rmi
```

## Build Dockerfile from local path
```
docker build -f 'path/to/Dockerfile' .
```

## See docker stats from docker-compose containers
```
docker stats --format "table {{.Name}}\t{{.CPUPerc}}\t{{.MemUsage}}\t{{.MemPerc}}\t{{.NetIO}}\t{{.BlockIO}}\t{{.PIDs}}"
```
[Source](https://gist.github.com/petermodzelewski/1567a711a9f26a5764a7)
