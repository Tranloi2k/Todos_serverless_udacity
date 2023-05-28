Serverless API for TODOS app

Services used in the project: Lamda, API gateway, DynamoDB, S3

Function:
  - Fetch list todos
  - Create list todos
  - Update list todos
  - Delete list todos
  - Update status
  - Upload image

Project structure:
└── backend
    ├── serverless.yml                    #Configure parameters such as service, provider, functions, events to define the resources and configuration.
    └── src
        ├── auth
        └── lambda
            ├── auth
            │   └── auth0Authorizer.ts    #User authentication and authorization in the project using Auth0
            └── http
                ├── createTodo.ts         #Use to create todos
                ├── deleteTodo.ts         #Use to delete todos
                ├── generateUploadUrl.ts  #Call S3 to gen signedUrl to upload image
                ├── getTodos.ts           #Get all todos
                └── updateTodo.ts         #Use to update todos
            

Step to complete the project:
  Step1: configure serverless.yaml - Configure service, provider, functions, events to define the resources and configuration
                                   - Add parameters like environment variables, permissions, and triggers to customize the app.
  Step2: update BE stater code     - Add function to update status of todo. (When create new todo, đefault status will be "in-process". 
                                     But user can update it later)
  Step3: Updete FE code            - Update FE to display status, handle action update status
  Step4: Deploy API                
  
To deploy BE:
npm install
sls deploy -v

Config in FE:

const apiId = '0aia6lzyy0' 
export const apiEndpoint = `https://${apiId}.execute-api.us-east-1.amazonaws.com/dev`
export const authConfig = {

  domain: 'dev-6us7cc5pwe0r7xbz.us.auth0.com',            // Auth0 domain
  clientId: 'YYeaaupwobsR9k5JdGfA1nw4KVG3iAfd',          // Auth0 client id
  callbackUrl: 'http://localhost:3000/callback'
}


user can update status by click to pencil button
please run my FE to use new feature
