# Docker cheatsheet

**Docker image**: Conponent (OS, library, etc) encapsulated with its configuration in order to instanciate one of more containers.
**Docker container**: Instance of a docker image, running on a Docker

## Docker Container commands

### Start a container
With this command, docker will start a container. If the container doesn't exists yet, it will download it from the docker hub (This only happen the first time a container is run).
```Python
# Here we'll run a NodeJs container
docker run nodejs
```

### Listing all running containers
Useful to know the currently executer containers. It provides the list of the names of the container, that we can use later to stop a specific container.
```Python
# List all the running containers
docker ps

# List all the running and previously closed containers
# docker ps -a
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


