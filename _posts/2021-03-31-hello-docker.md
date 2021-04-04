---
title: "Hello Docker"
excerpt: "Now, I use Docker"

categories:
  - Env
tags:
  - Env
last_modified_at: 2021-03-31T22:00:00-05:00
---

I decided to use Docker to manage my development environments (I use Ubuntu 20.04.02 LTS.).



## Installing Docker on Ubuntu

- Type the following commands in your terminal to install Docker.



### 1. Set up the repository

```
$ sudo apt-get update
```



```
$ sudo apt-get install -y apt-transport-https
$ sudo apt-get install -y ca-certificates
$ sudo apt-get install -y curl
$ sudo apt-get install -y gnupg-agent
$ sudo apt-get install -y software-properties-common
```



```
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo apt-key fingerprint 0EBFCD88
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```



### 2. Install docker engine -community

```
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```



### 3. usermod

- To run docker without typing `sudo`, 

```
$ sudo usermode -aG docker $USER
```

- This requires rebooting of your system.



## Installing Nvidia Docker

- Nvidia Docker should be installed to use a GPU (infrastructure) in your system, because Docker is separated with the OS.
- Nvidia driver need to be installed on your system prior to install Nvidia Docker. This can be checked at **Settings > Software & Updates**.

<img src="/Users/yodacat/Documents/repository-a/acousticwave.github.io/assets/images/2021-03-31-hello-docker_nvidia-driver-ubuntu.png" alt="2021-03-31-hello-docker_nvidia-driver-ubuntu" style="zoom:80%;" />



- Nvidia-Docker can be installed using the following commands

```
$ distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
$ curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
$ curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list

$ sudo apt-get update & sudo apt-get install -y nvidia-container-toolkit
$ sudo systemctl restart docker
```



## Building a Pytorch container



### 1. Downloading an image

- Pytorch containers, built by many users, can be pulled to your system.
- Docker containers are uploaded on [docker hub](https://hub.docker.com/).
- In my case, I pulled [a pytorch with pytorch-geometric container](https://hub.docker.com/r/fjvallarino/pytorch-geometric).

```
$ docker pull fjvallarino/pytorch-geometric
```

- The following command lists the downloaded images

```
$ docker images
```



### 2. Building a Pytorch container which utilize nvidia-docker

- The first step is 





## References

- [Pytorch and Jupyternotebook on Docker](https://89douner.tistory.com/96?category=878197) (in Korean)



## Future plan

- GitHub: how to