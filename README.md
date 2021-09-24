# Machine learning engineer challenge

## Problem definition  

Imagine you're working at a company building the next social sharing photo app to compete directly against Instagram. Everyone is hard at work to create the best user experience.

The product manager would like to add a new feature that automatically suggest tags to newly uploaded pictures. Those tags should be closely related to the content of the image being uploaded.

The data science team trains an image classification model which, given an image, returns the categories (or labels if you like) with their respective confidence score.

## Your task

The training of the ML model has been completed and the performance are deemed good enough to go to the production phase. [At this link](https://pytorch.org/hub/pytorch_vision_resnet/) you will find

- the trained model (use resnet18)
- a complete tutorial on how to interact with the model - i.e the expected input - and what result is returned

As a ML engineer your task is to put this machine learning model to good use. The application architecture looks like the following

```text
                                                      +-------+                             
                                         ------------>|       |                             
                                         |            |       | Service 1                   
                                         |            |       |                             
                                         |            +-------+                             
                                         |                                                  
+-----+                +------------+    |                                                  
|     |                |            |<---+                                                  
|  a  |     Rest       |            |                 +-------+                             
|  p  | <----------->  |  backend   |<------------->  |       |                             
|  p  |                |            |                 |       | Service 2                   
|     |                |            | <--+            |       |                             
+-----+                +------------+    |            +-------+                             
                                         |                                                  
                                         |                                                  
                                         |                                                  
                                         |            +-------+                             
                                         |----------> |       |                             
                                                      |       | Service 3                   
                                                      |       |                             
                                                      +-------+                             
```

You need to build a rest service that allows the application to make use of the capability of the trained ML model.

The service should

- accept an image in a request
- return a response with at most five categories, ranked in descending order of confidence.

You will not deploy the model yourself but you'll need to rely on the DevOps team. The team has a set of requirements for a new service to be deployed:

- The service should be containerized so a dockerfile should be provided
- Proper documentation describing the service interface and examples of invocation should be provided

In a nutshell your job is to create a production ready rest service and then leave it to the DevOps team the job to deploy it to the Kubernets cluster.

## How to submit the assigment

Fork this repository into your own **private** one. Once you've completed the assignment add:

- @noiano
- @fabiofumarola

As readers.
