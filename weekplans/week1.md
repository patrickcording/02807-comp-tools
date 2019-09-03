# Week 1
## Reading
Command line tools
- [Data Science at the Command Line](https://www.datascienceatthecommandline.com/) 

Git
- [Beginner](https://www.atlassian.com/git/tutorials/what-is-version-control)
- [Getting started](https://www.atlassian.com/git/tutorials/setting-up-a-repository)
- [Collaborating](https://www.atlassian.com/git/tutorials/syncing)

## Introduction survey
If you didn't fill it out during the lecture, please take 2 minutes and answer the [introduction survey](https://forms.gle/PvCSxAmFKg5HWvLd9).

## Exercises
### Exercise 1
Download [this](https://raw.githubusercontent.com/patrickcording/02807-comp-tools/master/docker/work/data/access.log-sample) webserver access log and use command-line tools to count the number of unique IP addresses seen.

Can you achieve it in a one-liner?

### Exercise 2
Download the [Titanic](https://raw.githubusercontent.com/patrickcording/02807-comp-tools/demo/docker/work/data/titanic.csv) dataset.

Use command line tools to solve the following exercises.

- Determine how many columns the dataset has
- Count the number of rows where `survived` is true and `survived` is false
- Sample 100 rows from the dataset such that the ratio between true and false occurrences of `survived` is the same

### Exercise 3 (preparation for next time)
We have compiled a Docker image that contains Python, Jupyter, Spark, and all the packages that you need for the course. 

Please follow the below instructions for installing Docker and getting the Docker container up and running.

#### Installing Docker
- [Installing Docker on Linux](https://runnable.com/docker/install-docker-on-linux)
- [Installing Docker on macOS](https://runnable.com/docker/install-docker-on-macos)
- [Installing Docker on Windows](https://runnable.com/docker/install-docker-on-windows-10)

#### Running the container
Download the [Dockerfile](../docker/Dockerfile) and [docker-compose.yml](../docker/docker-compose.yml) and place them in the same directory.

Create a subdirectory named `work` in the same directory.

Open a shell, change directory to your directory, and write

```
docker-compose run --service-ports notebook
```

The required images are now being downloaded and built, and two Docker containers are started (one for Python, Jupyter and Spark, and one for MySQL, which we will use later in the course).

You should now see a shell-prompt looking something like this

```
jovyan@notebook-server:~$
```

This means that you have started the required Docker containers and you are logged in to the one that contains Jupyter (and other things).

You may log out by issuing `exit` and stop the containers with `docker-compose down`.

If you don't delete the images, starting the containers will be a lot faster the next time you do this.

### Exercise 4 (setting up a Git repository for your work)
At DTU you have access to a GitLab installation using your DTU credentials. In this exercise you will set up a repository for keeping your Jupyter notebooks under version control.

- Install Git on your computer
- Go to [https://gitlab.gbar.dtu.dk](https://gitlab.gbar.dtu.dk) to set up a Git repository
- Go to your `work` directory and initialize it as a Git repository (use `git init`)
- Add a dummy file and add it to your repository (use `touch`, `git add`)
- Set your GitLab repository as remote and push your files (see [this](https://help.github.com/en/articles/adding-an-existing-project-to-github-using-the-command-line)) 
- Use this setup to play around and familiarize yourself with Git

If you use this repository for tracking your work you will be able to roll back to old versions of your notebooks and work on them from other computers (using `clone`, `commit`, `push`).
