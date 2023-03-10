# Week 3 — Decentralized Authentication

### REQUIRED HOMEWORK

I completed all required homework. It was in 3 parts- setting up Cognito userpool, implementing Cognito in the frontend and then verifying authorization to the backend

#### Setting up Cognito Userpool

I set Cognito userpool using the console. I then created a user that was used to test the integration of Cognito with the app

#### Implementing Cognito to Frontend

This part involved adding Amplify as a dependency in the [package.json](/frontend-react-js/package.json). Amplify was then configured in the [App.js](/frontend-react-js/src/App.js) to integrate Cognito with the frontend using the Cognito userpoolID, web client ID and region as variables.All of the environment variables were added to the [docker compose file](/docker-compose.yml)

The next step was the implementation of Cognito for authentication to the [sign up](/frontend-react-js/src/pages/SignupPage.js), [sign in](/frontend-react-js/src/pages/SigninPage.js), [confirmation](/frontend-react-js/src/pages/ConfirmationPage.js) and [recovery](/frontend-react-js/src/pages/RecoverPage.js) pages of the frontend.

#### Implementing Jwt to authorize connections to backend

To implement this part, we created a [custom library](/backend-flask/lib/cognito_jwt_token.py) that loads jwt keys, extract the request header and verifies the signature. This library was then imported into the app.py and used to implement authorization of the user to access the backend from the home page.

To test that everything was implemented correctly, a new user was signed up using the app. Also additional code was added to [home_activities](/backend-flask/services/home_activities.p) to confirm that only an authorized user can view additional content on the homepage that required authorization. 

### HOMEWORK CHALLENGES

For homework challenge, I explored addition of SMS for MFA and verification and also using Federated Identity providers as sign up options. Both challenges had limitations that made it impossible to fully implement.

#### USING SMS FOR MFA

To practice my knowledge of AWS IAM, I created my own IAM role with permissions that allow Cognito publish SNS text message, rather than use the feature that allows Cognito create a role. I then started the process of using SMS for verification by verifying my phone number. To complete the process to let Cognito send messages, I would need to configure certain AWS service dependencies including requesting SNS spending limit increase etc

![service dependencies](/_docs/assets/SMSVerification.png)
