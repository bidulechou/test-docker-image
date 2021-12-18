# test-docker-image
Project intended to test command line tools installation and usage for system maintenance automation in Azure Cloud using Linux.

Docker images present a lot of advantages, notably for development but not only. 
It allows creating specific environments for running applications that will be the same from development to production.
Concerning development advantages, it allows creating test environments that will be new and clean every time you will launch your docker image. 
This is a real advantage for automation where reproducibility is one of its fundamentals.

One of the advantages of docker images is that you can embed only the tools you need and not a complete Linux system like in a Virtual Machine (VM). 
It is a good solution to reduce system footprint, will produce less computation than a complete system which allow gaining a lot of time.
Effectively gain of time is very valuable on the development side, because running docker image is incredibly more speed than provisioning a VM to execute test.

Another focused point is the security, because security level is not the same in development and production.
Sometimes it is not easy to apply all security needs on images or machines cause developers do not know how to do it. 
If ops furnish ISO PROD stripped (secured) images or VMs and there sources, devs can do there job which is not configuring machines without knowing good security rules.   

Concerning security, it is also another great advantage because with image sources you can create new images based on standard PROD validated images. 
You can build and use your new image in which you can add normal user which will use `sudo` command to execute administrative commands, and you can also limit which commands it can use in sudoers file for security reasons.
You can propose the addition of your application user and its limited rights to ops team that can validate it, and probably enforce security with the help of sec-ops.
You can also use some tools that you will need during development stage (i.e. for debugging) and which will not be present in the images for staging and production, just by sharing the same docker file template. 

As DevOps, I think that in enterprises systems, virtual machines and docker images should be produced by ops automated systems (VM's forges or CI/CD for docker images) and sources should be shared with devs to let them have access to standardized and secured ISO PROD systems.
Sharing docker files with devs let them adding needed development and debugging tools to the docker file using same docker file than prod deployed system to avoid possible problems due to problems of tools version number or other security problems or what else that can interfere.

## Testing Microsoft Azure Linux Command Line Tools
One of the fundamental goals of this project is to test how can be created an autonomous testing environment for command line tools like azure-cli, blobfuse or file share mount through SMB protocol.

