<h1 align="center">Docker Container</h1> <br>

#### What is the container in docker?

ans: It is a executable package of software that contains everything needed to run an application: runtime, system tools, libraries and setting. Actually is it a instance of image. like OOP in programming. 



### Docker containers

Docker defines seven states for a container: created, restarting, running, removing, paused, exited, and dead.
A container is running while any processing is executed. if no processes is running on container then it automatically stoped. 

0. Start a container detach mode(run background: I can not see the output)

``` dockerfile
docker run -d container_name/image_name
```

1. Start a container attach mode (run in foreground: I can see the output on my screen)
```dockerfile
docker run container_name/image_name
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

8. To stop all the container (requred to stop all container before)

```dockerfile
docker stop image_name
```
9. Detach running container (problem)

   

10. To attach the detach file 
```
docker attach frist_few_word_of_container_id
```

### cleaning the multiple image and continer( cleaning up the workspace)

1. Remove all running container 
```
docker container rm -f $(docker contaner ls -aq)
```
note -f for force -a for all -q for imge or container ids
2. Remove the images
```
docker image rm -f $(docker image ls -aq)
```
