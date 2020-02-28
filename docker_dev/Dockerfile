FROM python:3

RUN apt-get -y update 
RUN apt-get -y install git 
RUN pip install --upgrade pip 

EXPOSE 8000

# Create directories. 
# At least "data_in" needs to be mounted.
RUN mkdir /src
RUN mkdir /db
RUN mkdir /log
RUN mkdir /static
RUN mkdir /data_in
RUN mkdir /data

# RUN ls /

# Get software and install libraries.
WORKDIR /src/
RUN git clone https://github.com/sharkdata/sharkdata_py3.git
WORKDIR /src/sharkdata_py3/
RUN pip install --no-cache-dir -r requirements.txt 

# Django - create db and collect static.
RUN python manage.py makemigrations
RUN python manage.py migrate
RUN python manage.py collectstatic --noinput

# Django - run in development mode.
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
