FROM python:3

RUN apt-get -y update 
RUN apt-get -y upgrade 
RUN apt-get -y install git 
RUN pip install --upgrade pip 

EXPOSE 8000

# Get software and install libraries.
RUN mkdir /src
WORKDIR /src/
RUN git clone https://github.com/sharkdata/sharkdata_py3.git
WORKDIR /src/sharkdata_py3/
RUN pip install --no-cache-dir -r requirements.txt 
RUN pip install --no-cache-dir gunicorn
# RUN pip install --no-cache-dir psycopg2

# Django - create db and collect static.
### RUN python manage.py makemigrations
### RUN python manage.py migrate
### RUN python manage.py collectstatic --noinput

# Django - run in development mode.
### CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
