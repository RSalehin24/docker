**Interaction with container**

*Using tty*
> if the container provides a terminal or interaction option: provide tty option to the docker command to enable tty to interact with it ```-t```.
```bash
docker run -t ubuntu
```
> to send message from terminal to container ```-i```. Intructs to pass stdin to container.
```bash
docker run -it ubuntu
```
> run a command in a detached ubuntu container. pass a name to the container using ```--name``` command. ```sh``` refers to shell command. ```-c``` tells sh to read the following string as command.
```bash
docker run -d -it --name ubuntu24 ubuntu sh -c 'while true; do date; sleep 1; done'
```
> output the stdout of ubuntu24 container using ```logs``` command and ```-f``` option.
```bash
docker log -f ubuntu24
```
> ```pause``` and ```unpause``` ubuntu24 contianer to check whether the output behave as it should.
```bash
docker pause ubuntu24
# check
docker unpause ubuntu24
```
> attach to the running container
```bash
docker attach ubuntu24
```
> attach to the container to see the output only. without seeing providing stdin to the container.
```bash
docker attach
```

*Using exec*
> use ```docker exec``` to interact with the docker
```bash
docker exec ubuntu24 ls -la
```
> using ```exec``` run a bash shell in interative mode ```-it``` and run commands in the bash session. see information about running processes using ```ps aux``` 
```bash
docker exec -it ubuntu24 bash 
# inside the bash session : ps aux
```
<!-- > **Not relevant**
> kill the while loop without terminating the container.  
> terminating the container doesn't kill the while loop.  
> a *SIGTERM*: ```kill -15 <pid>``` doesn't also have any effect in most cases as it signals for graceful stop.
> use a *SIGKILL* ```kill -9 <pid>``` to kill the process.
> get the pid ```ps aux | grep '[w]hile true; do date; sleep 1; done'``` -->

> stop the ubuntu24: the container don't stop immediately by ```stop``` command. as it sends a *SIGTERM* graceful stop signal first and after the grace period it sends a *SIGKILL* signal
> To stop the contianer faster or immediatly we can to send *SIGKILL*.
```bash
docker kill ubuntu24
docker rm ubuntu24

docker rm --force ubuntu24  # this will work instead of running two commands
```
> automatically remove the container after it is exited
```bash
docker run -d --rm -it --name ubuntu24 ubuntu sh -c 'while true; do date; sleep 1; done'
```
> ```attach``` ubuntu24 container and hit``` ^+p, ^+q``` to detach from stdout sequence or read escape sequence.
> this will not remove the container unlike ```^+c``` as ```--rm``` is used 
```bash
docker attach ubuntu24
^+p ^+q
```

