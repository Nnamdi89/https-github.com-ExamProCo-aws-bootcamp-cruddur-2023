FROM python:3.10-slim-buster
#sets the directory from where the dockerfile and context wil be retrived
WORKDIR /backend-flask
#copies the text file that contains contains flask setup instructions and then installs it
COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt
#the use of 2 periods identify that we are copying everything in the current directory listed above i.e /backend-flask
COPY . .
#set environment variables so that it is fixed whenever the container is running
ENV FRONTEND_URL = "*"
ENV BACKEND_URL = "*"
ENV FLASK_ENV=development

EXPOSE ${PORT}
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]