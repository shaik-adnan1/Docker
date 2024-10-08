# `Docker`

## `What is Docker?`

- Virtualization software
- Makes developing and deploying Applications easier
- Packages application with all the necessary dependencies, configuration, system tools and runtime

### `Before Containers`

- Each developer needs to install and configure all services directly to their OS on their local machine
- Installation process is different for each OS environment
- Many steps, where something can go wrong

### `How containers work(top level overview)`

- With docker, the service you need is packaged in one single environment
- Postgres packaged with all dependencies and configs
- Now you don't have to go and install and run all the commands but
- just run one docker command and get all the setup ready...

* Commands are same for all OS
* Command same for all services
* Easy to run different versions of the same app without any conflicts

## `Deployment process before container`

~ Development team setups up and Artifact(instruction on how to install and configure app on the server)
~ For this scenario - installation and configuration's done directly on the server's OS

- Dependency version conflicts... etc...

## `Deployment process with container`

- Docker artifact includes everything the app needs
- Since the configuration is done already by the developer team
  there is no need to do and extra configuration by the OPS team.
- less room for errors
- Devops team - install Docker runtime on the server and run the Docker command to fetch and run the DOCKER Artifacts

## `VMS vs DOCKER`

- VMs - have both OS kernel and the application layer
- Docker - only has the application layer, so running linux images or containers on a windows OS is not possible
- Docker containers are light weight compared to the VMs
- it takes only seconds to start a Docker container whereas it usually takes minutes for VMs to start

```
In order to counter that issue Docker desktop was introduced. In Docker desktop, if you have a linux container or an Image, the desktop has a hypervisor layer with a light weight LINUX Distro(Distribution) that enables to have a Linux OS Kernel allowing us to run Linux images/containers on Windows or any other systems.
```

# `Docker Desktop`

## `Docker Desktop includes `

### `Docker Engine`

- A server with a long-running Daemon process "dockerd"
- Manages image and containers

### `Docker CLI - Client`

- Command Line Interface ("Docker") to interact with Docker server
- Execute Docker commands to start/stop... containers

### `GUI Client etc...`

# `Docker Images vs Docker Containers`

### `Docker Image`

- An Executable application artifact
- Includes app source code, but also complete environment configuration
- Application layer (JS App), Any services needed (node, npm), OS Layer (Linux)
- Add environment variables, create directories and files etcc...
  file
  |
  |** file
  |** file

### `Docker Container`

- Actually start the application
- A running instance of an image
- We can run multiple containers from an image

# `Docker Registry`

- A storage and distributions system for Docker Images
- Official images available for application like Redis, Mongo, Postgres
- Official images are maintained by software authors or in collaboration with Docker Community
- Docker hosts one of the biggest Docker Registry called `Docker Hub`

# `Docker commands `

### `List of Docker images`

`docker images`

### `List of running Containers`

`docker ps`

### `pull an image from docker registry`

`docker pull <imageName>` =>
`docker pull nginx`

### `for pulling a specific version`

`docker pull {name}:{version_tag} = Pull an Image from a registry` =>
`docker pull nginx:1.23`

### `Running a docker image without blocking the terminal`

`docker run -d {name}`

- here -d means "-detach" this will run the container in the background and not block the terminal

### `Checking the logs pf a running container running in the background `

`docker logs {container}`

### `Port binding command`

` docker -d -p {HOST_PORT}:{CONTAINER_PORT} nginx`
` docker -d -p {9000}:{80} nginx`

### `Lists all containers (stopped and running)`

`docker ps -a` = -a means --all

### `Starting/Stopping an existing or new container`

`docker start {CONTAINER_NAME}`
`docker start 6bfdf9c095f3`

`docker start {CONTAINER_NAME}`
`docker start 6bfdf9c095f3`

- you can get the container name from the `docker ps -a` command

### `Naming a container`

`docker run --name web-app -d 8 -p 080:80 nginx`

# `Port Binding`

- Application inside a docker container runs in an isolated Docker network
- So we need to expose the container port to the host (the machine the container runs on)
- `PORT BINDING: Bind the container's port to the host's port to make the service available to the outside world`
- This allows us to run the same app running on the same port multiple times

### `Port binding command`

` docker -d -p {HOST_PORT}:{CONTAINER_PORT} nginx`
` docker -d -p {9000}:{80} nginx`

# `Registry vs Repository`

### `Docker Registry`

- A service providing storage
- Collection of repositories

### `Docker Repository`

- Collection of related images with same name but different versions

```
- Same way Docker hub is a registry that stores images
- On docker hub you can host private or public repositories for your applications
```