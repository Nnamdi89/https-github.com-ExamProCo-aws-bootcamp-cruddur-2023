# Week 2 — Distributed Tracing

## Required Homework

I completed the following as required homework
- Instrumentation of tracing using Honeycomb
- Instrumentation using Xray recorder and Xray Daemon
- Instrumentation of error handling using Rollbar
- Configuring logger for using Cloudwatch logs 

All of the processes above involved similar steps as described below:

I installed the dependencies that are required by adding them to the [requirements.txt](/backend-flask/requirements.txt) in the backend-flask folder and then running ```pip install -r requirements.txt``` in the CLI.

The next step was then to import the respective relevant modules into the [app.py](/backend-flask/app.py) and initialize the instrumentation as described in the video tutorials.

Also every required environment variable e.g Honeycomb API Key, Rollbar access token etc was initialized within the CLI and then added to the [dockercompose](/docker-compose.yml) file

After each distributed tracing service was implemented, it was tested to ensure functionality by adding the appropriate code into the service of choice. For example, in [homeactivities.py](/backend-flask/services/home_activities.py), a trace was created with a span named home-activities-mock-data  and custom attributes named app.now and app.resultslength

### HOMEWORK CHALLENGE

For homework challenge, I created a custom attribute named UserId. The attribute adds a randomly chosen username in the home-activities-mock-data span each time the api/activities/home is called.

![customattributeuserID](/_docs/assets/week2homeworkchallenge/Week2_honeycomb_userid.png)

Below is an image of recent traces

![recent traces](/_docs/assets/week2homeworkchallenge/Week2_honeycomb_recenttraces.png)

I also ran custom queries including Heatmap by UserId, UserId by Count etc

![heatmap by userid](/_docs/assets/week2homeworkchallenge/Week3_honeycomb_customquery.png)

Finally, I created custom span and attribute in the [notifications_activities.py](/backend-flask/services/notification_activities.py)

![notification span](/_docs/assets/week2homeworkchallenge/Week2_honeycomb_customspan.png)

