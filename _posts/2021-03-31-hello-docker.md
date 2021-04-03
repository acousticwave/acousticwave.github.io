---
title: "Hello Docker"
excerpt: "Now, I use Docker"

categories:
  - Env
tags:
  - Env
last_modified_at: 2021-03-31T22:00:00-05:00
---

I decided to use Docker to manage my development environments. I use Ubuntu 20.04.02 LTS.



## Installing Docker on Ubuntu



### Set up the repository

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



### Installing docker engine -community

```
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```



## References

I read the following references to build my first github.io blog.

- [Pytorch and Jupyternotebook on Docker](https://89douner.tistory.com/96?category=878197) (in Korean)




## Future plan

- GitHub: how to