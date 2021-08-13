# Forecast Process Image
This folder contain the files which allow to create a Docker image for
the database of the Fauno tool. The image is based on Mongo 4.2 image.

## Volume
This section describe the volumes available in the images and their objectives

### /backup
This volume was created to share backups between host and guess

### /data/db
This volume is by defult in the original image of Mongo to store
all data of the container

### /data/conf
This volume is by defult in the original image of Mongo to store
a custom configuration for mongo

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
docker pull stevensotelo/fauno_db:latest
```

### Run
The following command describes how to execute an instance of the images like a Docker container, further
it connects a local folder (D:/my_folder/workdir) with the volume in the docker (/forecast/workdir).

``` bash
docker run --name fauno_db -p 27017:27017 --env-file ./.env -v D:/my_folder/workdir/data:/data/db -v D:/my_folder/workdir/backup:/backup -d stevensotelo/fauno_db:latest
```

### Generate backup
Yo can generate a backup of the database

``` bash

```