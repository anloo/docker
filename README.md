# SHARKdata - Docker

Docker can be used both for test and prod.

Main project page for SHARKdata: https://github.com/sharkdata

## Development

Normally, you don't need docker to develop SHARKdata.
Use Python 3 and set up a virtual environment. Then clone the code from GitHub:

    python3 -m venv venv
    source venv/bin/activate
    git clone https://github.com/sharkdata/sharkdata_py3.git
    cd sharkdata_py3
    pip install -r requirements.txt
    python manage.py makemigrations
    python manage.py migrate
    python manage.py runserver

    # Open a web browser. Address: localhost:8000
    # Add datasets (as zip files) and resources to "./data_in".

## Test

Docker-compose for sharkdata_test is similar to sharkdata_prod except for where the volumes are located.
For test they are placed outside the docker environment and therefore the sftp container is not needed.
Docker-compose for test contains a setup with "nginx - gunicorn - django" similar to the production version.

You can find a template for your setup here:
https://github.com/sharkdata/docker/tree/master/docker_test

There are desktop versions of docker for both Windows and macOS that can be used for local test.
Documentation and download/installation instructions can be found here: https://docs.docker.com

## Production

In the production version all volumes are placed inside the docker environments. 
A container with sftp support is used to add and remove data from the "data_in" volume.

You can find a template for your setup here:
https://github.com/sharkdata/docker/tree/master/docker_prod

There is also a script available to set up an Ubuntu server to run SHARKdata.
