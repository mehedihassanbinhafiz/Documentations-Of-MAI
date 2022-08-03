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
2. Running docker image in background (I can not see the output on my screen)
```dockerfile
docker run -d image_name
```
note: d means detached mode
3.  Running for certain time

```dockerfile
docker run image_name sleep 5
```
4. Download image form docker hub

```
docker pull image_name
```
5. remove an image
```
docker rmi image_name
```
note: make sure not container running on this image.



### Docker containers

Docker defines seven states for a container: created, restarting, running, removing, paused, exited, and dead.
A container is running while any processing is executed. if no processes is running on container then it automatically stoped. 

1. Start a container attach mode (run in foreground: I can see the output on my screen)
```dockerfile
docker run container_name
```
2. To view which containers are running
```dockerfile
docker ps
```
4. To view all container running or not 

```dockerfile
docker ps -a
```
5. Pause/unpause  a running  container

```dockerfile
docker pause <container_id>
docker unpause <container_id>
```
6. Stop/Start of running a container

```dockerfile
docker stop <container_id>
docker start <container_id>
```
7. Remove a container

```dockerfile
docker container rm <container_id>
```

8. To stop all the container

```dockerfile
docker stop image_name
```
9. To attaach the detach file 
```
docker attach frist_few_word_of_container_id
```

## cleaning the multiple image and continer( cleaning up the workspace)

1. Remove all running container 
```
docker container rm -f $(docker contaner ls -aq)
```
note -f for force -a for all -q for imge or container ids
2. Remove the images
```
docker image rm -f $(docker image ls -aq)
```
