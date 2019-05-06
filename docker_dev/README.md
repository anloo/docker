# SHARKdata - docker_dev

SHARKdata - Docker file for development. 

**Don't use this setup for production.**

Main project page: https://github.com/sharkdata 

## Prepare directories 

Example from macOS. 
Replace the path "/Users/username/docker_sharkdata" to match your setup.

    mkdir /Users/username/docker_sharkdata/data_in/datasets
    mkdir /Users/username/docker_sharkdata/data_in/resources

Add datasets and resource files to the folders. 
Datasets (as zip files) and resource files can be downloaded from http://sharkdata.se

## Create an image and run the Django server in a container

    mkdir sharkdata_dev
    cd sharkdata_dev
    
    git clone https://github.com/sharkdata/docker.git
    
    cd docker/docker_dev
    
    docker build --tag=sharkdata-dev .
    
    docker run --rm -v /Users/username/docker_sharkdata/data_in:/data_in -p 8000:8000 sharkdata-dev
    
    # Stop the container when finished by pressing CTRL-C.

If you want to edit the source code and test it, you can copy the embedded source code from the container and mount a volume for it outside the container. Instead of using the "docker run" command above, you can do the following:

    # Copy /src from the container.
    docker create -ti --name dummy sharkdata-dev /bin/bash
    docker cp dummy:/src /Users/username/docker_sharkdata/
    docker rm -fv dummy
    
    # Run it with /src from the file system.
    docker run --rm -v /Users/username/docker_sharkdata/data_in:/data_in -v /Users/username/docker_sharkdata/src:/src -p 8000:8000 sharkdata-dev

For more info about Docker: https://docs.docker.com/

## Run SHARKdata.se from localhost

Open a web browser and type in the address: "localhost:8000".

Go to the "Data administration" page and press "Update datasets..." and "Update resources...".
Username/password is apa/bepa for development.
