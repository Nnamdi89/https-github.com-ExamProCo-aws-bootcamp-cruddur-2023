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

I also ran DynamonDB and Postgres Containers locally and tested them to make sure that there were no issues. To do this, I updated my gitpod.yml to include code to install postgress sql client in gitpod and also added vscode extension for it. I then updated my dockercompose.yml with code that integrates Dynamodb and Postgres when the container is run 







