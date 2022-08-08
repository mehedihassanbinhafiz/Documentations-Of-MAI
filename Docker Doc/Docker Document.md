## some questions: 
1. What is docker image?
ans: docker image is a template that contains the program or application and all the dependencies requireds to run on docker. it is comparable to  Virtual Machine. One image can create multiple containers.

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



