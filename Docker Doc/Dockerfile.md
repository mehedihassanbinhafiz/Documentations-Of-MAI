## Some questions: 

1. What is Dockerfile
ans: it is a text file that contains all commands that need to run in the command line to asseble an image file.

2. in docker / represents root directory

## Format

``` 
INSTRUCTION arguments
```
Docker file must begin with FROM instruction. 
FORM instruction represents the parent image from where we will build.

3. List of INSTRUCTION is give bellow:

   - ADD
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

#### FROM instruction
The FROM instruction initializes a new build stage and sets the Base Image for subsequent instructions.


