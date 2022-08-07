<h1 align = 'center'>Docker architecture<h1> <br>


## The main difference of Docker and VM
![docker architecture](https://user-images.githubusercontent.com/93854636/183277319-42a39f40-0e56-46b0-8f4c-7f5cc124c518.gif)

## VM

1.  We can install different os on hypervisor then we can run different app

2. Then we can host our application on top of each guest OS.

## Docker
1. If host is linux based then docker will be linux based, if host will be macOS then docker will be mac os based.
2. all of the apps will be run as docker container. 

## Docker Daemon
Docker daemon is a thin layer between the containers and the Linux kernel. that runs in a OS and responsible for running containers.

## components
docker follows client server architecture. three main part of docker are Docker Client, Docker Host, Docker Registry. 

1. Docker Client:

Docker client uses commands and rest apis to communicate with docker daemon. When user use client terminal and run command, then terminat sends this command to docker daemon in the form of command or Rest apis requests.

docker client uses these command:
``` dockerfile
docker build
docker pull
docker run
```
2. Docker Host
Docker Host is used to provide an environment to execute and run applications. It contains the docker daemon, images, containers, networks, and storage.

3. Docker Registry
Docker registry manges and stores the docker images.
Public registry - it is also known as docker hub
Private registry - is used to share image within the enerprise.

## Docker Objects

1. Docker Image
  Docker images are the read-only binary templates used to create Docker Containers. 

2. Docker Container
  It is a executable package of software that contains everything needed to run an application: runtime, system tools, libraries and setting. Actually is it a instance of image. like OOP in programming.

3. Docker Networking

  Using Docker Networking, an isolated package can be communicated. Docker contains the following network drivers -

  - **Bridge -** Bridge is a default network driver for the container. It is used when multiple docker communicates with the same docker host.
  - **Host -** It is used when we don't need for network isolation between the container and the host.
  - **None -** It disables all the networking.
  - **Overlay -** Overlay offers Swarm services to communicate with each other. It enables containers to run on the different docker host. In Docker, an overlay network driver is used for multi-host network communication. 
  - **Macvlan -** Macvlan is used when we want to assign MAC addresses to the containers.

4. Docker Storage is used to store data on the container. Docker offers the following options for the Storage -
   - **Data Volume -** Data Volume provides the ability to create persistence storage. It also allows us to name volumes, list volumes, and containers associates with the volumes.
   - **Directory Mounts -** It is one of the best options for docker storage. It mounts a host's directory into a container.
   - **Storage Plugins -** It provides an ability to connect to external storage platforms.
