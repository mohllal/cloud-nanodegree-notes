# Section 1: Serverless Introduction

- What is ***Serverless***?
  - A buzzword (not a pattern/technology/architecture)
  - A spectrum of solutions:
    - Servers are managed by someone else.
    - Allow to scale up and down easily and automatically by service provider.
    - Pay for what you use (except for storage).
    - No administration.

- Benefits of Serveless:
  - Low entry barrier.
  - Cost efficient.
  - High-availability and scalability.

- Serverless Components
  - ***FaaS***: Function as a service: write code in individual functions and deploy them to a platform to be executed.
  - ***Datastores***: Storage of data.
  - ***Messaging***: Send messages from one application to another.
  - ***Services***: Services that provide functionalities where we don't need to manage servers; i.e. authentication, ML, video processing.

- Function as a Service:
  - Split application into small functions.
  - Event driven.
  - Pay per invocation.
  - Rest is handled by a cloud provider.
  - Lambda function vs AWS Lambda.

- Use cases for FaaS:
  - Mobile/web backends.
  - Realtime streaming,
  - Files processing.

- AWS Lambda limitations
  - At most 3GB of memory per execution.
  - Functions can run no more that 15 minutes.
  - Can only write files to `/tmp` folder.
  - Limited number of concurrent executions.
  - Event size up to 6 MB.

- How lambda functions are executed?
  - When we send a request to execute a Lambda function, AWS Lambda creates an environment to run that function. It starts a container for the specific environment and loads the function code into the environment. Then it sends an event to our function. The same process is repeated for all the other requests coming in.

- AWS lambda functions have there are 3 invocation types:
  - Request/response.
  - Asynchronous invocation.
  - Using AWS CLI.

- Errors are handled differently, depending on how we execute our function. When we use a Request/response method: If there's an error in the function, then it will return immediately to the caller, which can process the error from the Lambda function.

- When we use an Async method: Instead of returning an error to the user, AWSLambda will return HTTP 202 code to the user and it will store a request into an internal queue. Additionally, it will try to call the Lambda function up to 3 times. If all of those times result into an error, then it will store the event into a "dead-letter queue", which stores all the events that the Lambda function failed to process.