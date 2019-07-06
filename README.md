# cd-aws-cloudformation-ecs
cd-aws-cloudformation-ecs demo

# PreRequisities

- AWS CLI
- AWS ECR Image with timeoff-management-application app

# How to Run this AWS CloudFormation Deployment

In your AWS you must create a ECR Repository with the application:

https://github.com/arkhoss/timeoff-management-application

Once created the repository, build the image and push it.

```bash

git clone https://github.com/arkhoss/timeoff-management-application.git && cd timeoff-management-application

$(aws ecr get-login --no-include-email --region us-east-1)

docker build -t timeoff-management-application .

docker tag timeoff-management-application:latest ***REMOVED***.dkr.ecr.us-east-1.amazonaws.com/timeoff-management-application:latest

docker push ***REMOVED***.dkr.ecr.us-east-1.amazonaws.com/timeoff-management-application:latest
```

Then proceed to deploy the Application with the CloudFormation Template below, click the rocket!

Deploy | Region Name | Region | Launch Types
:---: | ------------ | ------------- | -------------
[🚀][us-east-1] | US East (N. Virginia) | us-east-1 | Fargate

[us-east-1]: https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/review?stackName=ECS-ContinuousDeployment&templateURL=https://s3.amazonaws.com/cd-aws-cloudformation-ecs/cd-aws-cloudformation-ecs.yml&param_LaunchType=Fargate

This repository is being created for Gorilla reasons ^^
