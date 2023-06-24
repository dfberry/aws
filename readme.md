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

