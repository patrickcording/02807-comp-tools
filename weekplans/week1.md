# Week 1
## Reading
Command line tools
- [Data Science at the Command Line](https://www.datascienceatthecommandline.com/) 

Git
- [Beginner](https://www.atlassian.com/git/tutorials/what-is-version-control)
- [Getting started](https://www.atlassian.com/git/tutorials/setting-up-a-repository)
- [Collaborating](https://www.atlassian.com/git/tutorials/syncing)

## Exercises
### Exercise 1
First download `binary_classification.csv`. Find out where the data is from and what the target column is.

### Exercise 2
Use command line tools to count the number of instances (rows) of the majority and minority class of `binary_classification.csv`.

### Exercise 3
Use command line tools to create a new CSV file that contains as many rows from the majority class as there are rows in the minority class.

### Exercise 4
Use command line tools to sample 100 rows randomly from `binary_classification.csv`.

### Exercise 5 (preparation for next time)
We have compiled a Docker image that contains Python, Jupyter, Spark, and all the packages that you need for the course. 

Please follow the below instructions for installing Docker and getting the Docker container up and running.

_This assumes that you are familiar with using a shell on whatever operating system you are using. If not, please spend some time familiarizing yourself with [the basics](http://swcarpentry.github.io/shell-novice/)._ 

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
jovyan@1c057f7e8119:~$
```

This means that you have started the required Docker containers and you are logged in to the one that contains Jupyter (and other things).

If you don't delete the images, starting the containers will be a lot faster the next time you do this.

### Exercise 6 (setting up a Git repository for your work)
At DTU you have access to a GitLab installation using your DTU credentials. In this exercise you will set up a repository for keeping your Jupyter notebooks under version control.

- Install Git on your computer
- Go to [https://gitlab.gbar.dtu.dk](https://gitlab.gbar.dtu.dk) to set up a Git repository
- Go to your `work` directory and initialize it as a Git repository (use `git init`)
- Add a dummy file and add it to your repository (use `touch`, `git add`)
- Set your GitLab repository as remote and push your files (see [this](https://help.github.com/en/articles/adding-an-existing-project-to-github-using-the-command-line)) 
- Use this setup to play around and familiarize yourself with Git

If you use this repository for tracking your work you will be able to roll back to old versions of your notebooks and work on them from other computers (using `clone`, `commit`, `push`).
