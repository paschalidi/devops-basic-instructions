### Show commands & management commands
```docker```
### Docker version info
```docker version```
### Show info like number of containers, etc
```docker info```


## WORKING WITH CONTAINERS
### Create an run a container in foreground
```docker container run -it -p 80:80 nginx```
### Create an run a container in background
```docker container run -d -p 80:80 nginx```
### Shorthand
```docker container run -d -p 80:80 nginx```
### Naming Containers
```docker container run -d -p 80:80 --name nginx-server nginx```

### List running containers
```docker container ls```
OR
```docker ps```
### List all containers (Even if not running)
```docker container ls -a```
### Stop container
```docker container stop [ID]```
### Stop all running containers
```docker stop $(docker ps -aq)```

### Remove container (Can not remove running containers, must stop first)
```docker container rm [ID]```
### To remove a running container use force(-f)
```docker container rm -f [ID]```
### Remove multiple containers
```docker container rm [ID] [ID] [ID]```
### Remove all containers
```docker rm $(docker ps -aq)```


## IMAGE COMMANDS
### List the images we have pulled
```docker image ls```
### We can also just pull down images
```docker pull [IMAGE]```
### Remove image
```docker image rm [IMAGE]```
### Remove all images
```docker rmi $(docker images -a -q)```

### Some sample container creation
####  NGINX:
```docker container run -d -p 80:80 --name nginx nginx``` 
(-p 80:80 is optional as it runs on 80 by default)
#### APACHE:
```docker container run -d -p 8080:80 --name apache httpd```
#### MONGODB:
```docker container run -d -p 27017:27017 --name mongo mongo```
### MYSQL:
```docker container run -d -p 3306:3306 --name mysql --env MYSQL_ROOT_PASSWORD=123456 mysql```


## CONTAINER INFO
### View info on container
```docker container inspect [NAME]```
### Specific property (--format)
```docker container inspect --format '{{ .NetworkSettings.IPAddress }}' [NAME]```
