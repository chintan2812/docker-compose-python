# docker-compose-python
Docker environment for python scripts
This is a base template for python in docker. The purpose of this repository is to make it easy to create, build and deploy python scripts with docker.

The container set is based on the official python:3.8.

Configuration
Put all your python module dependencies in the requirements.txt file. The dependencies will then be installed at build. All files in the same folder as the Dockerfile will be copied into /usr/src/app by the python base image.

Modify the docker-compose.yml and Dockerfile to your likings to configure exposed ports, volume mounts, extra files, scripts etc.

Using the image in development
To not have to rebuild the container each time you have updated your code. If you are using docker-compose, you can run the command:

docker-compose build && docker-compose run --rm app bash
This will build a docker image and with the dependencies in the requirements.txt file, and then run the container with the console attached.

If you are using the image with pure docker, you can use the following commands:

docker build -t my-python-app .
Note that you can also install the dependencies in requirements.txt after you entered the container.

Using the image in production or on a remote docker host
When the code is ready for production or you want to run it on a remote server, remove the volume mounts and add a storage volume/container to store your files. then run the code as a regular docker-compose container set.

docker-compose build
docker-compose up -d

![image](https://github.com/chintan2812/docker-compose-python/assets/142546141/4fd84360-1fe9-432a-8ce6-1de40787cab6)

access docker image on port 8000
![image](https://github.com/chintan2812/docker-compose-python/assets/142546141/e0f08343-da7b-4bd8-a37a-c9412fafd947)

