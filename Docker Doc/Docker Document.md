## some questions: 
1. What is docker image?
ans: docker image is a template that contains the program or application and all the dependencies requireds to run on docker. it is comparable to  Virtual Machine. One image can create multiple containers. 
2. What is the continier in docker?
ans: It is a executable package of software that contains everyting needed to run an application: runtime, system tools, libraries and setting. Actually is it a instance of image. like OOP in programming. 

<h1 align="center"> Documentation </h1>

### Docker image
1. View docker image
``` dockerfile
docker images
```
2. Running docker image in background
```dockerfile
docker run -d image_name
```
note: d means detached mode
3. Download image form docker hub

```
docker pull image_name
```
4. remove an imges
```
docker rmi image_name
```
note: make sure not container running on this image.



### Docker containers

Docker defines seven states for a container: created, restarting, running, removing, paused, exited, and dead.
A container is running while any processing is executed. if no processes is running on container then it automatically stoped. 

1. Start a container attach mode
```dockerfile
docker run container_name
```
2. To view which containers are running
```dockerfile
docker ps
```
3. To view all container running or not 
```dockerfile
docker ps -a
```
4. Pause/unpause  a running  container
```dockerfile
docker pause <container_id>
docker unpause <container_id>
```
5. Stop/Start of running a container
```dockerfile
docker stop <container_id>
docker start <container_id>
```
6. Remove a container
```dockerfile
docker container rm <container_id>
```

4. To stop all the container

```dockerfile
docker stop image_name
```

