# docker_dev

SHARKdata - Docker file for development. 

**Don't use this setup for production.**

Main project page: https://github.com/sharkdata 

## Prepare directories 

Example from macOS. 
Replace the path "/Users/name/docker_sharkdata" to match your setup.

    mkdir /Users/name/docker_sharkdata/data_in/datasets
    mkdir /Users/name/docker_sharkdata/data_in/resources

Add datasets and resource files to the folders. 
Datasets (as zip files) and resource files can be downloaded from http://sharkdata.se

## Create an image and run the Django server in a container

    mkdir sharkdata_dev
    cd sharkdata_dev
    
    git clone https://github.com/sharkdata/docker.git
    
    cd docker_dev
    
    docker build --tag=sharkdata-dev .
    
    docker run --rm -v /Users/name/docker_sharkdata/data_in:/data_in -p 8000:8000 sharkdata-dev
    
    # Stop the container when finished by pressing CTRL-C.

For more info about Docker: https://docs.docker.com/

## Run SHARKdata.se

Open a web browser and connect to: "localhost:8000".

Go to the "Data administration" page and press "Update datasets..." and "Update resources...".
Username/password is apa/bepa for development.
