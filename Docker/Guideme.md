### Why docker/containers are important for few reasons 
Kubernetes/Container orchestration
Running processes in isolated environments
Starting projects/auxilary services locally


### Containarization 
Containers are a way to package and distribute software applications in a way that makes them easy to deploy and run consistently across different environments. They allow you to package an application, along with all its dependencies and libraries, into a single unit that can be run on any machine with a container runtime, such as Docker.

Why containers 
- Everyone has different Operating systems
- Steps to run a project can vary based on OS
- Extremely harder to keep track of dependencies as project grows

Benefits of using containers 
- let you describe your configuration in a single file 
- can run in isolated system 
- makes local setup of OS projects a breeeze 
- makes installing auxilary services and databases eary 

** Docker is not the only way to make container  , docker is most popular containerization tool contaier run time **

## Containerizations vs Virtualization



## Docker cli 
- go to docker cli via command docker 
- docker --version 


### docker run -it ubuntu
- if image found is runs the new container else it downloads image from dockerhub
-  docker run -d -p 4000:27017 mongo 
- -p for port mapping   runs mongo on port 4000 
- -d for detched mode (terminal becomes free)

- docker container ls 
(shows all containers )
- docker container ls -a 
(shows all containers even stopped ones)

Every container has its own IP address and a unique MAC address. Name and id 

## docker start docker_name 
 (starts the specified container )

## docker stop docker_id
 (stops the specified container )

## docker run docker_name 
  (run a new docker container)


## docker exec <container_name> <command_name>
docker exec container_name ls     // list all files in container without starting the container

## docker exec -it <container_name> /bin/bash  // start bash shell inside a running container and run it as interactive session

Most of the big companies have their docker image published and we can use them to create our own images for different projects. We can also use these images as base images for creating new custom images for specific project or application.


## kil docker container 
- docker kill <containerid>
- docker kill 243948234324

- docker rm <containerid>  /// removes container 
- docker rmi <image name>

# Port mapping 
suppoose i run dovker run -it piyushgargdev/mynodeapp   ==> you see server running on port say 3000 

now on your device if you go to localhost:3000 you willnot be able to access the application that is running inside the container.

to access in the required port you have to do port mapping g

## docker run -it -p <host_port>:<container_port> <image_name>  
-  start bash shell inside a running container and run it as interactive session with host machine on specified ports.
- docker run -it -p 3000:3000 piyushgargdev/mynodeapp   ==> you see server running on port say3000 in localhost 

Sometimes we need to expose two port 
## docker run -it -p 8025:8025 -p 1025:1025 mailhog/mailhog

## Passing environment varaibles to docker container to pass extra variables 
docker -d -p 1025:1205 -e kye=value -e key=value     mailhog/mailhog 


