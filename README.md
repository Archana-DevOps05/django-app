# Simple Django App
This is a simple, minimal Django app intended to help understand the main aspects of working with Django.


# Setups docker
# Install Docker in your system:
sudo apt-get update 
sudo apt-get install docker.io -y

# Check Docker version 
docker --version

# Firstly Create Directory
mkdir simple django-app
cd simple django-app

##Lets make Dockerfile for build the Project:
vim Dockerfile
FROM python:3.7
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
RUN python cool_counters/manage.py migrate
CMD ["python", "cool_counters/manage.py", "runserver", "0.0.0.0:8000"]

# Build Image using Dockerfile
docker build -t counter-app .

##Check the docker images...
docker images
 # Create Container using docker image
 docker run -it -d -p 8000:8000 counter-app:latest

 ##Now check the running container...
 docker ps
 





