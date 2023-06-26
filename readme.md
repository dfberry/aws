AWS notes

## initial notes
no code yet
https://dev.to/aws-builders/sync-git-repository-from-github-to-aws-codecommit-with-terraform-4iap

deploy to aws from 
* codecommit as repository
* codecommit as mirror of repository

## Syntax files

* CloudFormation - resource listings and configurations?

## IDE 

* AWS Cloud9

## clis

* AWS - 
* CDK - resource management
* SAM - serverless applications

## serverless

* serverless and api gateway are much more tightly integrated
* [Sam Workshop](https://catalog.workshops.aws/complete-aws-sam/en-US/module-1-sam-setup/)
* lambda doesn't expose http endpoint, api gateway does
* [SAM template](https://catalog.workshops.aws/complete-aws-sam/en-US/module-1-sam-setup/30-template) represents the serverless architecture, `template.yml`
  * Defines both the function configuration and the events that can trigger the function
  * You can change the name or location of your handler function via the CodeUri and Handler keys in the SAM template.yaml file.
* Can run full function app with gateway (`sam local start-api --port 8080`) or a single function (with SAM CLI like `sam local invoke --event events/event.json`)
* Function endpoints are separate from function handlers
* Equal amounts of docs/blogs show:
  * 1 API function via handler
  * N API function via passthrough proxy `/{proxy+}:` in `template.yml`. The proxy+ syntax is specific to AWS API Gateway and AWS Lambda and is not a standard feature of the OpenAPI Specification. [Example from SUSE](https://github.com/SUSE-Enceladus/public-cloud-info-service/blob/master/template.yaml#L56) - No API gateway transformation
* Docker is part of the local development experience
* Much higher degree of use of portal/console to create function apps and integrate with gateway

## resources

* [How to Create AWS CDK Lambda Functions](https://hevodata.com/learn/aws-cdk-lambda/)
* [Run express REST api as Lambda](https://www.moesif.com/blog/technical/api-development/Building-a-RESTful-API-With-AWS-Lambda-and-Express/)
* [Video](https://www.youtube.com/watch?v=dTSXizKXj2o)

## Run locally

1. Start docker

2. Start local server
  
  ```
  sam local start-api --port 8080
  ```

3. Change code. If JS, you do not need to restart the sam local process. You do need to save your application code file!