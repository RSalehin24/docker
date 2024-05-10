**Commands**
```bash
docker image pull <image>  # pulls image from a docker registry
docker run <image>  # downloads image(if not present locally), then creates and runs a container locally
docker run -d nginx  # downloads image(if not present locally), then creates and runs a container locally in the background ( & )
docker image ls  # list local images
docker container ls  # list running local containers only
docker ps # alternate : docker container ls
docker container ls -a # list all local containers
docker image rm <image> # remove image from local machine
docker image prune  # remove images those are unnamed and unused 
docker container run <image>  # runs a container from an image
docker container exec <container>  # executes a command inside the container
docker container stop  <container>  # stop a container (can use part of id which is unique)
docker container rm <container> # remove multiple containers from local machine
docker container prune  # remove all stopped containers
docker system prune # clears almost everything
```

**Commands, description and shortcut**

| Command | Description | Shortcut |
|:--------|:------------|:---------|
|```docker image pull```| Pulls image from a docker registry|```docker pull```|
|```docker image ls```| List all images |```docker images```|
|```docker image rm <image>```| Removes an image |```docker rmi```|
|```docker image prune```| Removes dangling images | --- |
|```docker image prune -a```| Removes dangling or unused images | --- |
|```docker container ls```| List running containers |```docker ps```|
|```docker container ls -a```| List all containers |```docker ps -a```|
|```docker container run <image>```| Runs a container from an image |```docker run```|
|```docker container run -d <imager>```| Runs a contianer from an image in detached mode | ```docker run -d```|
|```docker container stop <container>```| Stops a container | ```docker stop```|
|```docker container rm <container>```| Removes a container |```docker rm```|
|```docker container prune```| Removes all stopped containers | --- |
|```docker container exec <container>```| Executes a command inside the container |```docker exec```| 
|```docker system prune```| Clears almost everything | --- |

**Notes**
- To stop, remove or run an image/container use its name, id or portion of its id which is unique.
