# Week 3 — Decentralized Authentication

## REQUIRED HOMEWORK

I completed all required homework. It was in 3 parts- setting up Cognito userpool, implementing Cognito in the frontend and then verifying authorization to the backend

#### Setting up Cognito Userpool

I set Cognito userpool using the console. I then created a user that was used to test the integration of Cognito with the app

#### Implementing Cognito to Frontend

This part involved adding Amplify as a dependency in the [package.json](/frontend-react-js/package.json). Amplify was then configured in the [App.js](/frontend-react-js/src/App.js) to integrate Cognito with the frontend using the Cognito userpoolID, web client ID and region as variables.All of the environment variables were added to the [docker compose file](/docker-compose.yml)

The next step was the implementation of Cognito for authentication to the [sign up](/frontend-react-js/src/pages/SignupPage.js), [sign in](/frontend-react-js/src/pages/SigninPage.js), [confirmation](/frontend-react-js/src/pages/ConfirmationPage.js) and [recovery](/frontend-react-js/src/pages/RecoverPage.js) pages of the frontend.
