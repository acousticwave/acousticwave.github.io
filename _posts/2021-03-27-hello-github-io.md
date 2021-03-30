---
title: "Hello github.io"
excerpt: "I started blogging with github.io"

categories:
  - Blog
tags:
  - Blog
last_modified_at: 2021-03-27T17:00:00-05:00
---

I started blogging with github.io to record/manage progress on my studies and works. I started with a very popular theme [mininmal-mistake](https://github.com/mmistakes/minimal-mistakes). More than 7.8k users starred this theme.



## Host Minimal Mistake on the Web

### Clone Minimal mistake

- The first step is cloning the theme to your GitHub folder in your PC.

```
$ git clone https://github.com/mmistakes/minimal-mistakes.git
```

- Change the folder name **minimal-mistake** to **[username].github.io**. In my case, folder name is set as **acousticwave.github.io**.



### Hosting your blog

- You need to build a repository to host your blog (the folder **acousticwave.github.io**). A new repository can be created on GitHub webpage. Repository name is set as **acousticwave.github.io**.

![](https://github.com/acousticwave/acousticwave.github.io/blob/master/assets/images/2021-03-27-hello-github-io-new-repo.png)

- Remove the origin in the folder, add a new origin,  and push.

```
$ git remote remove origin
$ git remote add origin https://acousticwave.github.io/blog/hello-github-io.git
$ git push -u origin master

Counting objects: 16138, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (6166/6166), done.
Writing objects: 100% (16138/16138), 43.23 MiB | 7.45 MiB/s, done.
Total 16138 (delta 9709), reused 16138 (delta 9709)
remote: Resolving deltas: 100% (9709/9709), done.
To https://github.com/acousticwave/acousticwave.github.io.git
 * [new branch]        master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```

- Go to **[username].github.io** and check.



## How to write a page

*(Coming Soon!)*

### Write a first page

- Make a "_posts" folder



### Inserting an image

- "_asset/image"



### Checking a page locally

- M



## Category, Main page

*(Coming Soon!)*



## References

I read the following references to build my first github.io blog.

- [Building my blog with github.io](https://devinlife.com/howto%20github%20pages/new-blog-from-template/) (in Korean)

- [Writing the first post](https://devinlife.com/howto%20github%20pages/first-post/) (in Korean)
- [Inserting image and tables](https://devinlife.com/howto%20github%20pages/markdown-syntax/) (in Korean)
- [Other](https://devinlife.com/howto/)



## Future plan

- GitHub: how to
- My datasets and codes
- Autopilot
- VDR generator
- ROS, Docker
- CA algorithm, Ship maneuberability