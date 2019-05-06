FROM python:3.7-slim 

ENV PYTHONUNBUFFERED 1

EXPOSE 8000

RUN apt-get -y update 
RUN pip install --upgrade pip 

# Create directories. 
RUN mkdir /sharkdata_py3
RUN mkdir /static
RUN mkdir /config
RUN mkdir /data_in
RUN mkdir /data
RUN mkdir /db
RUN mkdir /log

# Install.
COPY src/sharkdata_py3/requirements.txt /config/requirements.txt
RUN pip install --no-cache-dir -r /config/requirements.txt
RUN pip install --no-cache-dir gunicorn
# RUN pip install --no-cache-dir psycopg2

# Set default directory for containers.
WORKDIR /sharkdata_py3
