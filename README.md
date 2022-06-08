# Docker-Studies

## Docker Commands

`Docker run <image>` - It runs a instance of the application if the image exists on the Host. If the image doesn't exist, Docker will pick those images on Docker Hub and download it (just the first time)

`Docker ps` - Lists all containers running

`Docker ps -a` Lists all containers, even those that are not running.

`Docker stop <container_name>` Stops a container

`Docker rm <container_name>` Removes a container

`Docker images` List of images

`Docker rm i <image_name>` Removes an image from Docker.

`Docker pull <image_name>` Is used to download an Image but not executing it.

Running a container attached:

This means that you will see the output of the container on your cli, but you will not be able to interact with the terminal until you end the process (ctrl + c)

`Docker run <image_name>` It's used to run an image (Does not run a OS).

Running a container detached:

`Docker run -d <image_name>`

Running a container detached will simply run a container as a background task, so you will be able to do other things inside the same terminal, without the need of opening a new window.

If you want to attach again to the container, run:

`Docker attach <container_id>`

It's possible to provide the first few characters of the id instead of everything.

If you want to execute some system specific command you can run:

`Docker run ubuntu sleep 5`

We can change this by creating a dockerfile and specifying on it

Dockerfile example:

```
FROM ubuntu

CMD sleep 5
```

OR

```
FROM ubuntu

CMD ["sleep","5"]
```


This way the container will sleep for 5 seconds.


If we change CMD by ENTRYPOINT the container will as much as we need


```
FROM ubuntu

ENTRYPOINT ["sleep"]
```

Running

`Docker run sleeper-image 10` 

Will make the container sleepy for 10 seconds

BUT if we don't specify anything we will get an error, so we need to add CMD after the entrypoint as a default parameter such as:

```
FROM ubuntu

ENTRYPOINT ["sleep"]

CMD["1"]
```



`Docker exec <container_name> <command>` This executes a command inside the container such as:

`Docker exec silly_shawarma cat /etc/hosts`

This command above will print the /etc/hosts content.


## Docker Run

`Docker run image:tag`

To run a specific version of an app, just add `:`and the version.

I.E.

`Docker run redis:4.0`

This command will run redis version 4.0

If no tag is specified the default tag will be `latest`


at (Docker Hub)[https://hub.docker.com/] We need to look for `supported tags`.

⚠️ Attention:

Containers don't listen for STDIN (Standard Input) by default

If we want to listen for user input and prompt things into the terminal we should use:

`Docker run -it <image>`

`-i` stands for: `interactive mode`

`-t` stands for: `sudo Terminal`

Using ports

`Docker run -p <external_port>:<internal_port> <image>`

To persist data outside a container we need to specify the external folder as below:

`Docker run -v path/to/persistent/data <image>`

To see all details about a container run:

`Docker inspect <container_name>`

This will print all the details of the container.

To see the logs of a specific container run:

`Docker logs <container_name>`

Adding environment variables to a Docker container:
After modifying the application run:

`Docker run -e APP_COLOR=red <image>:<tag>`

`-e` stands for environment variable.

To inspect environment varialbes of a container use

`Docker inspect <container_name>`

You will see the environment variables inside `"Config"->"Env"``




## Docker compose

Is used to setup a complex application, running several containers with one command.

It's applicable when running containers in only one host.
















