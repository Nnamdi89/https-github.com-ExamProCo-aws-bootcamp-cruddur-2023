# Week 1 — App Containerization

## Required Homework

I followed along with the instructions and completed the required homework.

Specifically, I created docker files for both the [frontend-react-js](/frontend-react-js/Dockerfile) and [backend-flask](/backend-flask/Dockerfile), after which I containerized the applications by running the appropriate docker commands to build the individual images and then run the containers   

Then I wrote a flask backend endpoint for the notification feature. This was done in the 3 steps below:
- Create a [notifications_activities.py](/backend-flask/services/notifications_activities.py) service 
- update the [app.py](/backend-flask/app.py) file to include a route for the notifications service
- update the [Open API](/backend-flask/openapi-3.0.yml) to include the API 'GET' method for notifications

I wrote a React page for Notifications by creating a [notificationfeedpages.js](/frontend-react-js/src/pages/NotificationsFeedPage.js), and then updating the [App.js](/frontend-react-js/src/App.js)

After confirming that the individual containers run without any issues, I created a [docker compose file](/docker-compose.yml) in the root of my project and ran the docker compose up command to build the multiple containers into a functional piece that integrated front and backend of the application.

**I learnt from tinkering with the dockerfile for the frontend-react-js that environment variables can be set within the dockerfile to ensure that whenever a container is run from the image created by the dockerfile, the variables are available**

I also ran DynamonDB and Postgres Containers locally and tested them to make sure that there were no issues. 

To do this, I updated my [gitpod.yml](/.gitpod.yml) to include code to install postgress sql client in gitpod and also added vscode extension for it. I then updated my dockercompose.yml with code that integrates Dynamodb and Postgres when the container is run.

## Homework Challenges

For my homework challenges, I did the following:

- Installed Docker on my local machine and got the same containers running outside of Gitpod
- Pushed and tagged images to Dockerhub
- Pulled Docker images from Dockerhub in Gitpod
- Created ECR and pushed images to Amazon Elastic Container Registry
- Run containers using images stored in Amazon ECR

Below are the details of the completed challenges

#### Installing Docker and running containers locally

1. I watched the docker fundamentals video by Adam Cantril. It is a brilliant, easy to understand tutorial. I then downloaded the Docker Desktop App. I did quite a bit of research and troubleshooting to get the app to work properly including installing a previous version and clean and purge data.
2. I cloned my github repo into my local machine using ```git clone https://github.com/Nnamdi89/https-github.com-ExamProCo-aws-bootcamp-cruddur-2023.git``` 
3. I then ran the appropriate docker command in the directory of choice

 ![backend-flask image](/_docs/assets/week1_homeworkchallenge/Week1_homeworkchallenge_dockerbuild_backend.png)
 ![backend-flask image](/_docs/assets/week1_homeworkchallenge/Week1_dockerbackend_image.png)
 ![backend-flask image](/_docs/assets/week1_homeworkchallenge/Week1_backend_container.png)
 ![backend-flask image](/_docs/assets/week1_homeworkchallenge/Week1backend-flaskrunninglocalhost.png)

4. I did same for frontend-react-js 
 ![frontend-react-js image](/_docs/assets/week1_homeworkchallenge/week1dockerbuildfrontendimage.png)

#### Push and Tag images to Dockerhub

5. I signed up for a free account on dockerhub, then created a public repository named [augustineezugwu/cloudprojectbootcamp](https://hub.docker.com/r/augustineezugwu/cloudprojectbootcamp)
6. Then I logged in via the command line, tagged the images and then pushed it to dockerhub
![docker_push_dockerhub]()




