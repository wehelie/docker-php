# Docker 

### docker info
- number of containers you have running
- number of images stored in docker


### How to get list of all Docker commands

just type `>docker`

### Commands:
```
  attach      Attach local standard input, output, and error streams to a running container
  build       Build an image from a Dockerfile
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  events      Get real time events from the server
  exec        Run a command in a running container
  export      Export a container's filesystem as a tar archive
  history     Show the history of an image
  images      List images
  import      Import the contents from a tarball to create a filesystem image
  info        Display system-wide information
  inspect     Return low-level information on Docker objects
  kill        Kill one or more running containers
  load        Load an image from a tar archive or STDIN
  login       Log in to a Docker registry
  logout      Log out from a Docker registry
  logs        Fetch the logs of a container
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  ps          List containers
  pull        Pull an image or a repository from a registry
  push        Push an image or a repository to a registry
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  rmi         Remove one or more images
  run         Run a command in a new container
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  search      Search the Docker Hub for images
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  version     Show the Docker version information
  wait        Block until one or more containers stop, then print their exit codes
```


### Docker command format:

new "management command" format 

> docker <command> <sub-command> (options)


# Image vs. Conatiners

An Image is the application we want to run
	- binaries
	- source code

A Container is an instance of that image running as a process
- You can have many containers running off the same image

# Starting a Nginx Webserver

> docker container run --publish 80:80 nginx

What is happenning? 
- Download image 'nginx' form Docker Hub
- Started a new container from that image
- Opened port 80 on the host IP

If we don't want to run this in the foreground, we can add the following:

> docker container run --publish 80:80 --detach nginx

Now, it is running the background. We also get back a unique container id. 

# docker container ls 
- lists running containers 

- names are generated from an open-source list of scientists and hackers i.e. priceless_pare

However, you can specify name for a container by running the following command

> docker container run --publish 80:80 --detach --name webhost nginx


# docker container stop + (container id)
- stops containers but does not remove it


# How to see logs for --detached containers

> docker container logs [name of the host]

To get more options, you can use --help


# Remove Containers

> docker container rm [container id(s)]


# What happens in the background when we run the `docker container run` command

1. looks for the image specified at the end of the command locally in image cache

if it does not find it there, 

2. Then it looks in the remote image repo (defaults to Docker Hub)

3. Downloads the latest version (nginx: latest by default)










