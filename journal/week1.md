# Week 1 — App Containerization

Installed Docker extension in VSCode
Created a dockerfile in the backend-flask folder and set environment variables for FRONTEND_URL = '*' and BACKEND_URL = '*'
```
FROM python:3.10-slim-buster

WORKDIR /backend-flask

COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

COPY . .
# setting the frontend_url and backend_url environment variables in the docker file ensures that any container that is run using the image created by this dockerfile will contain those variables
ENV FRONTEND_URL = '*'

ENV BACKEND_URL = '*'

ENV FLASK_ENV=development

EXPOSE ${PORT}
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]

```
Built image using docker build command 
```
docker build -t  backend-flask .
```
Ran a container using the image above

```
# --rm ensures that when the container is stopped, it is removed from the docker engine. omit if that fnctionality is not desired. Refer to docker documentation for docker commands

docker run --rm -p 4567:4567 -it backend-flask
```
Then followed all the steps for installing the frontend 
Then used Docker compose to build multiple containers (front and backend) that need to communicate with each other locally





