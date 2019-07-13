# Week 1
## Reading
Command line tools
- [Data Science at the Command Line](https://www.datascienceatthecommandline.com/) 

git
- [Beginner](https://www.atlassian.com/git/tutorials/what-is-version-control)
- [Getting started](https://www.atlassian.com/git/tutorials/setting-up-a-repository)
- [Collaborating](https://www.atlassian.com/git/tutorials/syncing)

## Setup
We have compiled a Docker image that contains Python, Jupyter, Spark, and all the packages that you need for the course. 

Please follow the below instructions for installing Docker and getting the Docker container up and running.

_This assumes that you are familiar with using a shell on whatever operating system you are using. If not, please spend some time familiarizing yourself with [the basics](http://swcarpentry.github.io/shell-novice/)._ 

### Installing Docker
- [Installing Docker on Linux](https://runnable.com/docker/install-docker-on-linux)
- [Installing Docker on macOS](https://runnable.com/docker/install-docker-on-macos)
- [Installing Docker on Windows](https://runnable.com/docker/install-docker-on-windows-10)

### Running the container
Download the [Dockerfile](../docker/Dockerfile) and [docker-compose.yml](../docker/docker-compose.yml) and place them in the same directory.

Create a subdirectory named `work` in the same directory.

Open a shell, change directory to your directory, and write

```
docker-compose run --service-ports notebook
```

The required images are now being downloaded and built, and two Docker containers are started (one for Python, Jupyter and Spark, and one for MySQL, which we will use later in the course).

You should now see a shell-prompt looking something like this

```
jovyan@1c057f7e8119:~$
```

This means that you have started the required Docker containers and you are logged in to the one that contains Jupyter (and other things).

If you don't delete the images, starting the containers will be a lot faster the next time you do this.

## Exercises