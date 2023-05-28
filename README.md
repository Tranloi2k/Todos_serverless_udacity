# Serverless API for TODOS app

## Services used in the project: Lamda, API gateway, DynamoDB, S3

## Function:
  - Fetch list todos
  - Create list todos
  - Update list todos
  - Delete list todos
  - Update status
  - Upload image

## Project structure:

![image](https://github.com/Tranloi2k/Todos_serverless_udacity/assets/87125486/00dbe335-2184-4a7b-9a9d-7bdb388487ce)


## Step to complete the project:
  Step1: configure serverless.yaml 
  - Configure service, provider, functions, events to define the resources and configuration
  - Add parameters like environment variables, permissions, and triggers to customize the app.
  Step2: update BE stater code     
  - Add function to update status of todo. (When create new todo, đefault status will be "in-process".  But user can update it later)
  Step3: Updete FE code            
  - Update FE to display status, handle action update status
  Step4: Deploy API                
  
## To deploy BE:
```bash
npm install
sls deploy -v
````
## Config in FE:
```bash
const apiId = '0aia6lzyy0' 
export const apiEndpoint = `https://${apiId}.execute-api.us-east-1.amazonaws.com/dev`
export const authConfig = {

  domain: 'dev-6us7cc5pwe0r7xbz.us.auth0.com',            // Auth0 domain
  clientId: 'YYeaaupwobsR9k5JdGfA1nw4KVG3iAfd',          // Auth0 client id
  callbackUrl: 'http://localhost:3000/callback'
}
````

user can update status by click to pencil button
please run my FE to use new feature
