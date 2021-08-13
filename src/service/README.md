# FAUNO service Image
This folder contain the files which allow to create a Docker image for
the service of the Fauno tool. The image is based on Python:3.9-slim

## Files
This section is created to describe the function of some files,
which are contained into this folder

### Dockerfile
The Dockerfile contains the definition of the image.

### example.env
This file contains a definition of all envrioment variables which are needed
in order to run a container based on this images. In the example that you will
see in the following steps, you will see a file called **.env**, this file
is an instance of **example.env**, the difference is that **.env** file has the values setted.

## How to use
The following section explains a couple of things that you should take into account when you
are trying to run the image.

### Install
The installation process requires that **Docker** system is installed. Once you have installed
the Docker you just need to execute the following command, which download the image form Docker hub:

``` bash
docker pull stevensotelo/fauno_service:latest
```

### Run
The following command describes how to execute an instance of the images like a Docker container, further
it connects a local folder (D:/my_folder/workdir) with the volume in the docker (/forecast/workdir).

``` bash
docker run -d --rm --env-file ./.env  -p 5000:80 --name fauno_service stevensotelo/fauno_service:latest
```
