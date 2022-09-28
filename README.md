## Sample application
### Let’s create a simple Python application using the Flask framework that we’ll use as our example. Create a directory  in your local machine named python-docker and follow the steps below to create a simple web server.

     
     pip3 install Flask
     pip3 freeze | grep Flask >> requirements.txt
     python3 -m flask run

##  Create a Dockerfile for Python

add a line in our Dockerfile that tells Docker what base image we would like to use for our application.

     FROM python:3.8-slim-buster
     WORKDIR /app
     COPY requirements.txt requirements.txt
     RUN pip3 install -r requirements.txt
     COPY . .
     CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0"]



## Build Docker Image


     docker build -t python-example .


## Run the image 

     docker run -p 5000:5000 python-example


