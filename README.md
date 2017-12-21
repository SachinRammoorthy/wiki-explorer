# Wikipedia Explorer

[![Codacy Badge](https://api.codacy.com/project/badge/Grade/187f571b72344e4eab4c4d95c0e45503)]


## <a id="desc"></a>What is this project about?
This project provides a simple client for searching for Wikipedia articles using the Wikipedia API.


## <a id="setup"></a>Setting up the project
* [Installing Docker](#ins_docker)
* [Installing Docker-compose](#ins_docker-compose)
* [Load the configuration file](#ins_load_conf)
* [Configuring the site](#ins_conf_site)


### <a id="ins_docker"></a>Installing Docker
On the official Docker website, you can download the software for any operating system. However, if you want to work on Windows, be prepared for the fact that the Docker starts services in this virtual environment (for example, via VirtualBox), which affects performance.

Run the following on terminal/cmd:
```bash
$sudo apt update
$sudo apt install apt-transport-https ca-certificates
$sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-keys  58118  E89F3A912897C070ADBF76221572C52609D
```
```bash
$sudo apt update
$sudo apt install docker-engine
$sudo service docker start
```


### <a id="ins_docker-compose"></a>Installing Docker-compose
Run the following on terminal/cmd:
```bash
$curl -L "https://github.com/docker/compose/releases/download/1.8.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
$chmod +x /usr/local/bin/docker-compose  
$docker-compose --version
```


### <a id="ins_load_conf"></a>Load the configuration file
After Docker has installed, download the configs prepared by the JBoss team. To do this, use Git and *clone* the repository. You need to execute these commands from the directory where you want to store all the files of our site.
```bash
$git clone git@github.com:codex-team/docker.git codex-docker
$cd codex-docker
```
Next, execute the commands that load all the necessary packages and collect the container.
```bash
$docker-compose build
$docker-compose up
```
Now you have a container ready to work with any sites that use Nginx, PHP, etc. Do not close the current console (it will run docker-compose).
In the *www* directory, you can now start creating a site or clone the repository and work on it.


### <a id="ins_conf_site"></a>Configuring the site

Now, let's move on to the direct configuration site. Open a new terminal window. The first step is to download the source code to the *www* folder.
```bash
 $git clone https://github.com/jboss-outreach/wiki-explorer.git www
```
In your docker folder there is a *www* directory where all the necessary files are located. This folder will be *shared*, that is, it will be used simultaneously and virtual containers and your local operating system.
Run the docker ps command to find the name of the container.
To make the site available at http://wiki-explorer.dev:8081/ from your local machine, add it to the hosts file.
```bash
$echo "127.0.0.1 codex.dev" >> /etc/hosts
```
Now you can go to the site at http://localhost:8081/ or http://wiki-explorer.dev:8081/.


## Contributing to the project
1. Make your intended changes on your locally cloned repository.

2.Commit the changes and push the commit to your forked repository on GitHub.

3.Ensure the changes on the commit pushed to your GitHub fork are right and bug-free.

4.Create a pull request requesting to merge the commits on your fork to this repository.

5.Write a concise and convincing pull request message explaining the purpose of your commits.


For more help regarding the Wikipedia API, refer this manual:
* [Using the Wikipedia API](doc/API.md)
