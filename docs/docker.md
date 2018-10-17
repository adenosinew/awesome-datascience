# Intro to docker

[TOC]

Resource:

[Docker concepts](https://hackernoon.com/docker-commands-the-ultimate-cheat-sheet-994ac78e2888) <- recommend

[kaggle docker](http://blog.kaggle.com/2016/02/05/how-to-get-started-with-data-science-in-containers/)

[Awesome Docker](https://github.com/veggiemonk/awesome-docker)

[Docker cheat sheet](https://github.com/wsargent/docker-cheat-sheet)



Tools & Plugins:

For *oh-my-zsh*, add "docker" to the ```.zshrc``` file for auto-completion of docker command. e.g.

```shell
# ~/.zshrc
plugins=(
  git
  autopep8
  dirhistory
  docker
  python
)
```



## Installation

Go to the docker website and find a correspond method for your system.



## Must-known docker concepts


Before we get into the best practices for using Docker, here’s a quick overview of the vocabulary you should know:

- **Layer**: a set of read-only files or commands that describe how to set up the underlying system beneath the container. Layers are built on top of each other, and each one represents a change to the filesystem.
- **Image**: an immutable layer that forms the base of the container.
- **Container**: an instance of the image that can be executed as an independent application. The container has a mutable layer that lies on top of the image and that is separate from the underlying layers.
- **Registry**: a storage and content delivery system used for distributing Docker images.
- **Repository**: a collection of related Docker images, often different versions of the same application.





## Docker commands

### **Developing with Docker Containers**:

- **docker create [image]**: Create a new container from a particular image.
- **docker login**: Log into the Docker Hub repository.
- **docker pull [image]**: Pull an image from the [Docker Hub repository](https://hub.docker.com/).
- **docker push [username/image]**: Push an image to the Docker Hub repository.
- **docker search [term]**: Search the Docker Hub repository for a particular term.
- **docker tag [source] [target]**: Create a target tag or alias that refers to a source image.

### **Running Docker Containers**

- **docker start [container]**: Start a particular container.
- **docker stop [container]**: Stop a particular container.
- **docker exec -ti [container] [command]**: Run a shell command inside a particular container.
- **docker run -ti — image [image] [container] [command]**: Create and start a container at the same time, and then run a command inside it.
- **docker run -ti — rm — image [image][container] [command]**: Create and start a container at the same time, run a command inside it, and then remove the container after executing the command.
- docker pause [container]: Pause all processes running within a particular container.

### **Using Docker Utilities:**

- **docker history [image]**: Display the history of a particular image.
- **docker images**: List all of the images that are currently stored on the system.
- **docker inspect [object]:** Display low-level information about a particular Docker object.
- **docker ps**: List all of the containers that are currently running.
- **docker version**: Display the version of Docker that is currently installed on the system.

### **Cleaning Up Your Docker Environment:**

- **docker kill [container]**: Kill a particular container.
- **docker kill $(docker ps -q)**: Kill all containers that are currently running.
- **docker rm [container]**: Delete a particular container that is not currently running.
- **docker rm $(docker ps -a -q)**: Delete all containers that are not currently running.

### **Update Your Docker Environment:**

- Update all images: **docker images |grep -v REPOSITORY|awk '{print $1}'|xargs -L1 docker pull**
- 


## Data science docker best practice

Purpose: Install kagge kernel image

step 1: pull the image

```shell
docker pull kaggle/python:latest
```

step 2: run the container

