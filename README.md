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

This way the container will sleep for 5 seconds.

`Docker exec <container_name> <command>` This executes a command inside the container such as:

`Docker exec silly_shawarma cat /etc/hosts`

This command above will print the /etc/hosts content.






