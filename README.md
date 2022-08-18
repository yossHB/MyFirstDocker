# Everything about Docker
Get started with Docker Compose


1. [Overview](#Overview)
   * [Definition](#Definition)
   * [Docker Setup](#docker-setup)
     * [Windows](#windows)
     * [macOS](#macos)
     * [ubuntu](#ubuntu)
1. [Command](#Command)
1. [Create a snapshot in docker](#create-a-snapshot-in-docker)
1. [Push an image on the DockerHub](#Push-an-image-on-the-DockerHub)
1. [Docker Networking](#Docker-Networking)
1. [Going further](#Going-further)
   * [Docker - Kubernetes Architecture](#Docker-Kubernetes-Architecture)
   * [ Kubernetes vs Docker](#Kubernetes-vs-Docker)


## Overview
### Definition
  Docker is the de facto model for building and running containers at scale in most enterprise organizations today. 

  At a very high level, Docker is a combination of CLI and a daemon process that solves common software problems like installing, publishing, removing, and managing containers. 
  
  It’s perfect for microservices, where you have many services handling a typical business functionality; Docker makes the packaging easier, enabling you to encapsulate those services in containers.

  Once the application is inside a container, it’s easier to scale and even runs on different cloud platforms, like AWS, GCP, and Azure.

> **Note**  
>   if you want to access a course, I suggest this website [Docker-tutorial]

### Docker Setup
#### Windows

If you are using the legacy Hyper-V mode of _Docker Desktop for Windows_, ensure [File Sharing][win-filesharing] is
enabled for the `C:` drive.

#### macOS

The default configuration of _Docker Desktop for Mac_ allows mounting files from `/Users/`, `/Volume/`, `/private/`,
`/tmp` and `/var/folders` exclusively. Make sure the repository is cloned in one of those locations or follow the
instructions from the [documentation][mac-filesharing] to add more locations.

#### ubuntu

The Docker installation package available in the official Ubuntu repository may not be the latest version. To ensure we get the latest version, we’ll install Docker from the official Docker repository [documentation][ubuntu-filesharing]. 


## Command 

1. start up your application by running 
```
$ docker compose up 
```
to run your services in the background, you can pass the -d flag (for “detached” mode) to docker compose up.
```
$ docker compose up -d
```
2. docker inspect <tag or id>
``` 
$ docker image ls
```
3. Stop the application
```
$ docker compose down
```

4. to see what is currently running
```
$ docker compose ps
```
5. to see what environment variables are available to the web service 
```
$ docker compose run web env
```
6. stop your services
```
$ docker compose stop
```
- Pass --volumes to also remove the data volume used by the Redis container 
```
$ docker compose down --volumes
```
To read more the other [Command][reference]

## Create a snapshot in docker
To create a new image from a container’s changes
```console
$ docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
```
Refer to the options section for an overview of available OPTIONS for this command.
Read more about the available [OPTIONS][options]

## Push an image on the DockerHub
To push an image or a repository to a registry
```console
$  docker push [OPTIONS] NAME[:TAG]
```
To read more about the To [Command][Push]

## Docker Networking

In this part, we are going to talk about diffrent type of docker networking
1. The Default Bridge network
1. The User-defined Bridge network
1. The MACVLAN network
1. The trunked network: MACVLAN 802.1q
1. The IPVLAN network (L2/L3)
1. Overlay network
1. None network

### for more information
* [Docker Network | official website](https://docs.docker.com/network/)
* [Docker Network | youtube ](https://www.youtube.com/watch?v=bKFMS5C4CG0)


## Going further

### Docker Kubernetes Architecture
>  Kubernetes is an orchestration framework for Docker containers which helps expose containers as services to the outside world. 

### Kubernetes vs Docker

>Docker Swarm, a standalone container orchestration engine for Docker containers, offers native clustering capabilities with lower barriers to entry and fewer commands than Kubernetes. Swarm users are encouraged to use Docker infrastructure, but are not blocked from using other infrastructures. 
>
>In recent years, the two containerization technologies have begun to operate most efficiently when used together. Docker enables a business to run, create and manage containers on a single operating system. With Kubernetes, containers can then be automated for provisioning, networking, load balancing, security and scaling across nodes from a single Dashboard.
>
>Mirantis acquired the Docker Enterprise business in late 2019 and initially intended to focus on Kubernetes, but later pledged to support and expand the enterprise version of Docker Swarm.



[Docker-tutorial]: https://www.tutorialspoint.com/docker/index.htm
[options]: https://docs.docker.com/engine/reference/commandline/commit/#options

[reference]: https://docs.docker.com/engine/reference/run/
[Push]:https://docs.docker.com/engine/reference/commandline/push/