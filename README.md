# SHARKdata - Docker. 

Docker can be used for development, test and production.  

Main project page: https://github.com/sharkdata 

## Single docker file

Normally, you don't need docker to develop SHARKdata. Just use Python 3 and set up a virtual environment for all installed packages.

But if you don't want to install Python, then it is possible to run SHARKdata on your local machine by using the docker file described here: 
https://github.com/sharkdata/docker/tree/master/docker_dev 

It contains the source code and all installed packages needed, as well as a sqlite database.

## Docker compose

Docker compose is recommended for installation if you want to run SHARKdata on a public server. 

You can find a template for your setup here: 
https://github.com/sharkdata/docker/tree/master/docker_test 

It contains a setup with "nginx - gunicorn - django" that can be extended for both test and production. 

## Install docker

There are desktop versions of docker for both Windows and macOS that can be used for development. 

Documentation and download/installation instructions can be found here: https://docs.docker.com 

