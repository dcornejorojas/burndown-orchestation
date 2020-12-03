# Burndown-orchestation

Repo with git_modules to build the burden-server environment.

## Prerequisites

This environment use a docker-compose file for the build with git modules for the services, so you need to check if you have at least this component installed:
* Git: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git
* Docker: https://docs.docker.com/engine/installation/
* Docker-Compose: https://docs.docker.com/compose/install/

In your shell you must run this commands.

```shell
$ git -v
$ docker -v
$ docker-compose -v
```

## Clone the repo and setup the development environment

On the git server (localhost), login with your git user we'll clone the development-local git repo, 
add the various application modules
to it, populate it with the docker files we need to configure.

```shell
$ git clone https://github.com/dcornejorojas/burndown-orchestration.git burndown-orchestration
Cloning into 'burndown-orchestration'...
```

## Update submodules

With the cloned repo, you must noticed that the submodules are empty, so you need to "pull" each submodule.

```shell
$ git submodule foreach 'git pull origin master'
```

This line run a git pull origin of each 'master' branch in the submodules (if one of them don´t have a master branch, it won´t retrieve nothing)

If you already cloned the project and forgot --recurse-submodules, you can combine the git submodule init and git submodule update steps by running git submodule update --init. To also initialize, fetch and checkout any nested submodules, you can use the foolproof 

```shell
$ git submodule update --init --recursive.
```

## Build the project

Once you have updated all submodules, you are able to build the project, for that you need to run the following commands.

```shell
$ docker-compose build
```

If all goes well, you can see the submodules containers running.
Now you will run the docker-compose.

```shell
$ docker-compose up
```
