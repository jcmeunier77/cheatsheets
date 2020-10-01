# Docker cheatsheet

**Docker image**: Conponent (OS, library, etc) encapsulated with its configuration in order to instanciate one of more containers.
**Docker container**: Instance of a docker image, running on a Docker client.

Container are designed to run a specific task: When an application finish its executions (or when it crashed), docker will close the container.

## Docker Container commands

### Start a container
With this command, docker will start a container. If the container doesn't exists yet, it will download it from the docker hub (This only happen the first time a container is run).
```Python
# Here we'll run a NodeJs container
docker run -d nodejs
```
The `-d` parameter means "detached": The container is run in the background, you won't see its logs appearing on your console.

#### Starting in interactive mode
Some application requires to get inputs from the command line. However, by default, docker start in non-interactive mode. To **start in interactive mode**, add `-i` to the run command. And to show the commands prompted by your application, you need to **start in terminal mode** with the `-it` parameter:

```Python
# Run in interactive mode (no prompt allowed for the appplication, but interactiond are allowed)
docker run -i nodejs

# Run in interactive-terminal mode (application's prompt and interactions are allowed)
docker run -it nodejs
```
Now, you can type your command direclty to the app currently runnin, as if the app was running direclty in your console.

#### Specifying an image version
You can **specify the desired version** of a image by adding a version tag:
```Python
docker run -d nodejs:14.11.0-strech
# Find tags of an image on: https://hub.docker.com/_/node?tab=description
```

### Attach to a container
To see the logs of a currently running container, attach to it
```Python
docker attach container_name
```

### Listing all running containers
Useful to know the currently executer containers. It provides the list of the names of the container, that we can use later to stop a specific container.
```Python
# List all the running containers
docker ps

# List all the running and previously closed containers
docker ps -a
```

### Stop a container
```Python
docker stop nodejs
```

### Remove a container
To remove a container and clean all used space.
```Python
docker rm nodejs
```

## Docker Image commands

### Download a docker image
This is an alternative to `docker run`: It will only download a docker image without running it.
```Python
docker pull nodejs
```

### List all images stored locally
List all images downloaded and stored locally. Usefull to later remove these images.
```Python
docker images
```

### Remove a docker image
To remove a docker image and clean all used space.
**Warning**: You must remove all containers using this images before removing it !
```Python
docker rmi nodejs
```

## Execute commands inside running containers

With `docker exec`, you can execute a command inside a docker container.
### Example: Displaying a file in a container
```Python
# container_name is the name of your container.
docker exec container_name cat /etc/hosts
```
