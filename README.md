# Wikipedia Explorer

[![Build Status](https://travis-ci.org/jboss-outreach/wiki-explorer.svg?branch=master)](https://travis-ci.org/jboss-outreach/wiki-explorer)

[![Codacy Badge](https://api.codacy.com/project/badge/Grade/187f571b72344e4eab4c4d95c0e45503)]

[![Gitter chat](https://badges.gitter.im/gitterHQ/services.png)](https://gitter.im/jboss-outreach)

## Contents
* [What is Wikipedia Explorer?](#desc)
* [Setting up](#setup)
* [Contributing](#contribute)
* [Additional Learning](#learning)

## <a id="desc"></a> What is Wikipedia Explorer?
This project provides a simple client for searching for Wikipedia articles using the Wikipedia API.


## <a id="setup"></a> Setting up the project
* [Installing Docker](#ins_docker)
* [Installing Docker-compose](#ins_docker-compose)
* [Load the configuration file](#ins_load_conf)
* [Configuring the site](#ins_conf_site)


### <a id="ins_docker"></a>Installing Docker
On the official Docker website, you can download the software for any operating system. However, if you want to work on Windows, be prepared for the fact that the Docker starts services in this virtual environment (for example, via VirtualBox), which affects performance.

Run the following on terminal/cmd:
```bash
$ sudo apt update
$ sudo apt install apt-transport-https ca-certificates
$ sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-keys  58118  E89F3A912897C070ADBF76221572C52609D
```
```bash
$ sudo apt update
$ sudo apt install docker-engine
$ sudo service docker start
```


### <a id="ins_docker-compose"></a>Installing Docker-compose
Run the following on terminal/cmd:
```bash
$ curl -L "https://github.com/docker/compose/releases/download/1.8.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
$ chmod +x /usr/local/bin/docker-compose  
$ docker-compose --version
```


### <a id="ins_load_conf"></a>Load the configuration file
After Docker has installed, download the configs prepared by the JBoss team. To do this, use Git and *clone* the repository. You need to execute these commands from the directory where you want to store all the files of our site.
```bash
$ git clone git@github.com:codex-team/docker.git codex-docker
$ cd codex-docker
```
Next, execute the commands that load all the necessary packages and collect the container.
```bash
$ docker-compose build
$ docker-compose up
```
Now you have a container ready to work with any sites that use Nginx, PHP, etc. Do not close the current console (it will run docker-compose).
In the *www* directory, you can now start creating a site or clone the repository and work on it.


### <a id="ins_conf_site"></a>Configuring the site

Now, let's move on to the direct configuration site. Open a new terminal window. The first step is to download the source code to the *www* folder.
```bash
 $ git clone https://github.com/jboss-outreach/wiki-explorer.git www
```
In your docker folder there is a *www* directory where all the necessary files are located. This folder will be *shared*, that is, it will be used simultaneously and virtual containers and your local operating system.
Run the docker ps command to find the name of the container.
To make the site available at http://wiki-explorer.dev:8081/ from your local machine, add it to the hosts file.
```bash
$ echo "127.0.0.1 codex.dev" >> /etc/hosts
```
Now you can go to the site at http://localhost:8081/ or http://wiki-explorer.dev:8081/.


## <a id="contribute"></a> Contributing to the project

**Step 1: Fork this project:**

Go to the top right of the project page and click on "Fork". A fork of this repo will be created on your GitHub account.

**Step 2: Code your changes**:

Create a new branch by:
```
$ git checkout -b YOUR_NEW_BRANCH_NAME
```
Then create/edit files as per your coding requirements. Ensure that your code is clean and efficient, and avoid redundancies. It is also advised to follow naming conventions as and where specified. Also make sure that your code is your own, and is not closed-source or stolen.

**Step 3: Commiting and pushing the changes:**

*Commit* the changes and *push* the commit to your forked repository on GitHub by:
```
# for including inidividual files
$ git add filename.extension
# for including all files at once
$ git add .
```
```
$ git commit -m"Your commit message here"
$ git push origin
```
If stuck at this point, refer [here](https://readwrite.com/2013/10/02/github-for-beginners-part-2/)

**Step 4: Sending a Pull Request (PR):**

Once you are done coding the changes, commit the files and create a [*PR*](https://help.github.com/articles/about-pull-requests/). Click on "Compare across forks" when creating the PR, and select the master branch of this repo as the base. Set the head to your branch on your fork. Click on the button "Create Pull Request". Give your PR a meaningful title and a brief message explaining the purpose of your commits.

**Step 5: Ensuring code quality**

Once a PR has been created, check if it can be merged without any issues or conflicts. If there are any issues, repeat from **Step 2** and try to resolve them. Wait for a reviewer to cross check your changes, and then merge your changes.

* Additional Reference regarding clone, fork and editing a repository [**here**](https://egghead.io/lessons/javascript-how-to-fork-and-clone-a-github-repository).

```
Keep Contributing to open source! =)
```


## <a id = "learning"> </a> Additional Learning

* [More about Wikipedia API](doc/API.md)
* [More about Contributing on Github](doc/CONTRIBUTING.md)
* [How to use GitHub](https://guides.github.com/activities/hello-world/)
* [Git commands handbook](https://git-scm.com/docs)
* [Chat with us!](https://gitter.im/jboss-outreach)

