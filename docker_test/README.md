# docker_test

SHARKdata - Docker file for test. 

**Don't use this setup for production.**

Main project page: https://github.com/sharkdata 

## File structure

Create a file structure based on the files that can be found here.

    docker_test
    - Dockerfile
    - docker-compose.yml
    - config
      - nginx
        - sharkdata_py3.conf
    - src

## Check out the source code 

    git clone https://github.com/sharkdata/sharkdata_py3.git src

## Build, start and stop

    docker-compose build

    docker-compose up -d

    docker-compose down # When finished.

## Test

Open a web browser and connect to: "localhost:8000" when it is running.

## Check logs

    docker-compose logs django_1

    docker-compose logs nginx_1




