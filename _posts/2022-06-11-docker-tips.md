---
title: "Docker - Tips"

excerpt: "Docker - Tips"

categories:
  - Docker

tags:
  - Docker

last_modified_at: 2022-06-11T17:00
---

## Container → Image

- Docker images

  - ```
    $ docker images
    REPOSITORY                      TAG       IMAGE ID       CREATED         SIZE
    fjvallarino/pytorch-geometric   latest    7ee3fe57718c   21 months ago   4.23GB
    ```

- Run the docker image as a container (or we can run the image on Docker Desktop)

  - ```
    $ docker run --name container_name fjvallarino/pytorch-geometric
    ```

- List running containers

  - ```
    $ docker ps
    CONTAINER ID   IMAGE                                  COMMAND       CREATED        STATUS         PORTS     NAMES
    cf66765c8f20   fjvallarino/pytorch-geometric:latest   "/bin/bash"   2 months ago   Up 8 seconds             container_name
    ```

- Running container → image 

  - ```$ docker commit -a [AUTHOR] -m [COMMIT MSG] [CONTAINER NAME] [REPO]:[TAG]```

  - ```
    $ docker commit -a "acousticwave" -m "commit_test" container_name acousticwave/pytorch-geometric:2022-06-11
    ```

- Check the built image

  - ```
    $ docker images
    REPOSITORY                       TAG          IMAGE ID       CREATED          SIZE
    acousticwave/pytorch-geometric   2022-06-11   a4cc2d1caf95   53 seconds ago   7.56GB
    ```



## Image → Remote Repo.

- Docker Desktop can pushs the built image to a remote remote repository

{% include figure image_path="/assets/images/2022-06-11-docker-tips-push-to-hub.png" alt="this is a placeholder image" caption="Images > Push to Hub" %}

- We can pull this image on other devices.

{% include figure image_path="/assets/images/2022-06-11-docker-tips-pull.png" alt="this is a placeholder image" caption="Remote Repo. > Pull" %}



## Sharing  Host Path with Container Path

- Docker Desktop support sharing a ```Host(Local) Path``` with ```Container Path```
  - Docker Desktop → Images  →  Run  → Operation Settings
    - Container Name: Set ```Container Name```
    - Volumes
      - ```Host Path```: Define a path to be shared with a container (files in this path are uploaded to ```Container Path```)
      - ```Container Path```: Path to be connected to ```Host Path```

{% include figure image_path="/assets/images/2022-06-11-docker-tips-new-container-0.png" alt="this is a placeholder image" caption="Docker Desktop > New Container" %}

{% include figure image_path="/assets/images/2022-06-11-docker-tips-new-container-1.png" alt="this is a placeholder image" caption="Container Name / Host Path / Container Path" %}



## Attaching a Container to Visual Studio Code

- Open a Visual Studio Code window and install **Docker** and **Remote Development** extensions.
- And Run a Container (Setting of ```Host Path``` and ```Container Path``` required as explained [above](## Sharing  Host Path with Container Path))
- Type ```Cmd + Shift + P ``` and  ```remote-containers: Attach to Running Container...```

{% include figure image_path="/assets/images/2022-06-11-docker-tips-remote-container.png" alt="this is a placeholder image" caption="remote-containers" %}

- Select a running container

{% include figure image_path="/assets/images/2022-06-11-docker-tips-select-running-container.png" alt="this is a placeholder image" caption="Running Container" %}

- VSCODE > Open Folder ... > Type  ```Container Path```

{% include figure image_path="/assets/images/2022-06-11-docker-tips-type-container-path.png" alt="this is a placeholder image" caption="Container Path" %}



## *Move an Image to Other Env (TBU)*

- List Docker images

  - ```
    $ docker images
    REPOSITORY                       TAG          IMAGE ID       CREATED          SIZE
    acousticwave/pytorch-geometric   2022-06-11   a4cc2d1caf95   53 seconds ago   7.56GB
    ```

- Docker image  → .tar file

  - ```docker save [OPTION] <FILENAME> [IMAGE-NAME]```

  - ```
    docker save
    ```

    

