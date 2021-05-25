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
