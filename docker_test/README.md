# docker_test

SHARKdata - Docker for test. 

This is a simple as possible setup for running "nginx - gunicorn - django" by using docker-compose.
Modify the sharkdata_py3.conf file if it should be accessed from other hosts than localhost.

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

    cd docker_test/src
    git clone https://github.com/sharkdata/sharkdata_py3.git 
    cd ..

## Build, start and stop

    docker-compose build

    docker-compose up -d

    docker-compose down # When finished.

## Test

Open a web browser and connect to: "localhost:8000" when it's running.

## Check logs

    docker-compose logs django

    docker-compose logs nginx




