# Docker-Into
Intro to Docker
# What is Docker Compared to a VM?

VM - Virtual Machine is a full installation of an OS. It is very large.
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
- Image - it is the additional layer. (Base OS, necessary files, Our file). Each of this layer is called an image.
Image is ReadOnly
- Container - If we want to run an image, we turn it to a container. We can create and destroy containers based on the image.
- Dockerfile - SetupFile. This file tells what to do.
Dockerfile is a script that tells you step by step what to do to create our image.

# Docker Commands
## Basic Commands
### Image
```
- docker build -t name:tag .        // build a new image
- docker images                     // show all images
- docker image history imageid      // to see the history of image 
- docker rmi imageid                // to remove image
```
### Container
```
- docker ps -a                      // show all containers
- docker stop conatinerid           // to stop a running container
- docker start containerid          // to start a container
- docker rm containerid             // removes the container
```
## To Run an image we have to create a conatiner.
```
- docker run -e "environmentvariable" -d --name container-name -p portnumberofmachine:portnumberofcontainer imagename:tag
```
// -e - environment variables (we can have multiple -e's)
// -d - stands for disconnect
// -p - map a port from container to our machine


After making more changes, we have to create a new image as a new version and replace old one

### There are many docker images available at the official website
[www.hub.docker.com](https://hub.docker.com/search?q=&type=image)


## Microsoft SQL Server
### Running MS SQL Server image :
script to build mssqlserver 2017 docker container
```
    docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=password" --name container-name -p 11433:1433 -d mcr.microsoft.com/mssql/server:2017-latest
```
Check if connection is working in cmd
```
    sqlcmd -S <localhost,1432> -U SA -P 'Pwd12345!'
```

### To Build image using code in dockerfile
```
    docker build -t container-name:version .
```
// This take the code inside dockerfile and executes it to build our own image
// according to what is there in the file and copies it on to the top of docker OS

### To Run the image and create a container
```
    docker run -p 11433:1433 -d restored-db --name sql-container
```
eg:-  `docker run --name mssql -p 1432:1433 -d restored-db`  -- This script Creates a container using restored-db image
    
