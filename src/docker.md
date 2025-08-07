<image alt="Docker Logo" height="100px" src="../images/docker.png" width="100px" />

# Docker

* Ensures consistency across environments.
* Allows you to ship an application and the environment it runs in.

## General
* Docker Daemon / Server - Listens to requests from the desktop app and executes them.
* Docker Desktop - The visual way to interact with Docker. Starting the GUI should start the Docker server.
* Docker CLI - Allows you to execute Docker commands through the command line.
* Docker Hub - The official cloud service for storing and sharking Docker images.
* Container - A standard unit of software that packages up code and all its dependencies, so the application runs quickly and reliably from one computing environment to another. Containers run instances of images.
* Image - A read-only definition of an application or container and everything it needs to run properly.
* Volume - A persistent data storage mechanism that allows data to be shared between a Docker container and the host machine.
* Network - A communication channel that enables different Docker containers to talk to each other or the external world. It creates connectivity. Allowing containers to share information or services while maintaining isolation.
* `Dockerfile` - A set of instructions telling Docker how to build an image.

## Commands
* `docker pull <image_name>` - Pulls an image from Docker Hub.
* `docker images` - Lists all your local images.
* `docker ps` - List all running images.
* `docker stop <container id> | <container name>` - Stops the specified container.