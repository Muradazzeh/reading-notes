## AWS: API, Dynamo and Lambda
 * What is Amazon API Gateway?
In this guide, we’ll walk you through all the details of API Gateway. We’ll show you how it can be used with the Serverless Framework and give you a list of resources should you want to learn even more.

Recently, AWS also launched AWS HTTP APIs. These are a potential alternative to API Gateway REST APIs that we discuss in detail in our Ultimate Guide to AWS HTTP APIs.

### How does API Gateway integrate with other AWS services?
Many AWS services support integration with Amazon API Gateway, including:

AWS Lambda: run Lambda functions to generate HTTP API responses.
AWS SNS: publish SNS notifications when an HTTP API endpoint is accessed.
Amazon Cognito: provide authentication and authorization for your HTTP APIs.
API Gateway supports direct integrations that can be configured in the API Gateway user interface (or via the API Gateway’s own API) for the following actions:

### Benefits of Amazon API Gateway
Using API Gateway to create HTTP APIs in AWS offers four main benefits:

* Map HTTP requests to specific functions in a Serverless application via an API Gateway event. Connecting HTTP endpoints to individual functions is straightforward with API Gateway, obviating the need for a dedicated API server.

* Map WebSocket events to Serverless functions. If you are building a WebSocket API, API Gateway also lets you map its events to a Serverless function. This works great for real-time functionality like in-app updates and notifications.

* Use multiple microservices to serve the same top-level API. API Gateway makes it easy to have different Serverless functions serving different parts of your API. This means you can better encapsulate your functionality into each function and clearly separate the business logic of different parts of your API. Another benefit here is that you can transparently replace the function called by a given API request—the users won’t notice any change on the API layer.

* Save time with integrations: authentication, developer portal, CloudTrail, CloudWatch. API Gateway allows you to implement a fully managed authentication and authorization layer by using Amazon Cognito and Lambda custom authorizers without running your own auth systems. By using API Gateway you also get access to the developer portals that are generated automatically from your API schemas. In addition, CloudTrail, CloudWatch and X-RAY all integrate with API Gateway, simplifying the profiling and debugging of API requests.

## Amazon API Gateway
* Amazon API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. APIs act as the "front door" for applications to access data, business logic, or functionality from your backend services. Using API Gateway, you can create RESTful APIs and WebSocket APIs that enable real-time two-way communication applications. API Gateway supports containerized and serverless workloads, as well as web applications.

* API Gateway handles all the tasks involved in accepting and processing up to hundreds of thousands of concurrent API calls, including traffic management, CORS support, authorization and access control, throttling, monitoring, and API version management. API Gateway has no minimum fees or startup costs. You pay for the API calls you receive and the amount of data transferred out and, with the API Gateway tiered pricing model, you can reduce your cost as your API usage scales.

## What is DynamoDB?
* DynamoDB is a hosted NoSQL database offered by Amazon Web Services (AWS). It offers:

* reliable performance even as it scales;
a managed experience, so you won't be SSH-ing into servers to upgrade the crypto libraries;
a small, simple API allowing for simple key-value access as well as more advanced query patterns.

## Dynamoose 
* is a modeling tool for Amazon's DynamoDB. Dynamoose is heavily inspired by Mongoose, which means if you are coming from Mongoose the syntax will be very familar.

* Key Features#
Type safety
High level API
Easy to use syntax
Ability to transform data before saving or retrieving documents
Strict data modeling (validation, required attributes, and more)
Support for DynamoDB Transactions
Powerful Conditional/Filtering Support
Callback & Promise support

```
npm install --save dynamoose
```
### Import
In order to use Dynamoose you must import it or require it in your project. This will make the dynamoose namespace accessible so you can use things like models, schemas, and more.

```
const dynamoose = require("dynamoose");
```
