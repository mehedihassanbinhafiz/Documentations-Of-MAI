## Some questions: 

1. What is Dockerfile
ans: it is a text file that contains all commands that need to run in the command line to assemble an image file. we can deploy only a single container with the help of the docker image. However, if you need to deploy several containers (each for different tasks) from the same image then we need Dockerfile

2. in docker / represents root directory

## Format 

``` 
INSTRUCTION arguments
```
Docker file must begin with FROM instruction. 
FORM instruction represents the parent image from where, we will build. Instruction also known as keyword.

3. List of INSTRUCTION is give bellow:

   - ADD
   - RUN
   - CMD
   - ENTRYPOINT
   - MAINTAINER
   - COPY
   - ENV
   - EXPOSE
   - FROM
   - LABEL
   - STOPSIGNAL
   - USER
   - VOLUME
   - WORKDIR
   - ONBUILD

#### FROM: 
It is used to define base or parent image from which we will be building.
### ADD:
It is used to add file to the container being build.
### RUN:
It is used to add layers to the base image by installing components. 
### CMD:
It is used to run commands at the start of the container. These commands run only when there is no argument specified while running the container.
### ENTRYPOINT:
It is used to run commad after docker image building. If we want to run container after running docker image then we have to use ENTRYPOINT. 
### ENV:
It is used to define environment variable. 
### EXPOSE:
It is used to specifiy listeing port to enable networking at runtime.
### MAINTAINER:
It is used to specify the name and email id of the image creator.
### USER:
It is used to specify the username used to run the container.
### VOLUME:
It is used to allow access from the container to the directory on the Docker host
### WORKDIR:
It is used to specify the path of the command to be executed at run time.
###  LABEL
It is used to add labels to the docker image.

## Building image from Dockerfile
