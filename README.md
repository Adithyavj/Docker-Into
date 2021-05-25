# Docker-Into
Intro to Docker
# What is Docker compared to a VM?

VM - Virtual Machine is a full installation of and OS. It is very large.
Virtual Machine runs on something that has an OS and Applications, one of which is the Virtual Machine Host (which runs VM)
it duplicates the OS.

Docker
- We have the Host OS with applications installed on it
- It doesn't install a whole new OS
- It does have an OS layer but it is tiny and pulled from the OS of host 
- OS with only bare minimum is installed, on top of it just the required things are installed.

Docker is a series of Layers. The first layer start off with the Host OS.
- If we are running linux, it runs on top of the windows sub system for linux.
- Stacking items on top of one another. (Only necessary things are put)
- The containers are reusable.

Docker key Terminology
- Image - it is the additional layer. (Base OS, necessary files, Our file). Each of this layer is called and image
Image is ReadOnly
- Container - If we want to run an image, we turn it to a container. We can create and destroy conatiners based on the image.
- Dockerfile - SetupFile. This file tells what to do.
Dockerfile is a script that tells you step by step what to do to create our image.

# Docker Commands
## Basic Commands
### Image
```
- docker images // show all images
- docker build -t name:tag . // build a new image
- docker image history imageid // to see the history of image 
```
### Container
```
- docker ps -a // show all containers
- docker stop conatinerid // to stop a running container
- docker start containerid // to start a container
- docker rm containerid // removes the container
```
## To Run an image we have to create a conatiner.
```
- docker run -d --name container-name -p portnumberofmachine:portnumberofcontainer imagename:tag
```
// -d - stands for disconnect
// -p - map a port from container to our machine