## Some Questions
What is docker Compose?
ans: Docker Compose is a tool that was developed to help define and share multi-container applications. With Compose, we can create a YAML file to define the services and with a single command.
It allows to deploy, combine, and configure multiple docker containers at the same time. 

**Docker Compose** is used to run multiple containers as a single service. 

1. check docker-compose version
2. docker-compose version 
```
docker-compose -version
docker-compose version
```
2. Create docker compose
The name of the file must be
```
docker-compose.ymlb
```
3. This file must start with version
[form this link](https://docs.docker.com/compose/compose-file/compose-file-v3/) we can map which compose  version support which docker  version. 
4. compose commnad
services: all services must be written bellow servies keyword
image: the image_name of a services specified in dockerhub.
ports: the ports keyword to mention the ports that need to be exposed for an image
environments: specify the environment variables for a image  which are required to run this image

5. Docker compose validity check
```
docker-compose config
```
5. compose run
```
docker-compose up

##detach mode
docker-compose up -d

```
6. compose stop
```
docker-compose down
```
### Scale Down Services
--scale: it set number of container for a service
format: docker-compose up -d --scale service_name=number_you want to run continer
```
docker-compose up -d --scale database=4
```





