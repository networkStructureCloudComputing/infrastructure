# Infrastructure
``CloudFormation - AWS``

## Features
* Create, Update, and Delete stack and its resources using cloud formation

## About the project
Created an vpc, subnets, internet gateway, routes, and route table using aws cloudformation

## How To Run
* Install and configure AWS CLI on your development machine from AWS Website.
* Create AWS CLI user profiles in Sandbox and Production account.
* Both Sandbox and Production AWS CLI profiles should be set to use the ``us-east-1`` region or the region closest to you.
* Clone the repository into your local machine using git clone command.
* Go to your project folder using cd
* Add a parameter.json file for configuration of the infra in which you want to build all your resources.

**Option 1**
* Set ``export AWS_PROFILE=[profile_name]`` or it can be any environment of your choice  
* Set ``export AWS_REGION=us-east-1`` or it can be any region of your choice
* Write command ```aws cloudformation create-stack --stack-name [stack_name] --template-body file://csye6225-infra.yml --parameters file://parameter.json``` to create stack and start the creation of the resources in aws
* Write command ```aws cloudformation update-stack --stack-name [stack_name] --template-body file://csye6225-infra.yml --parameters file://parameter.json``` to update exit stack and its resources
* Write command ```aws cloudformation delete-stack --stack-name [stack_name] ``` to delete the stack and its resources

**Option 2**
* Write command ```aws cloudformation deploy --stack-name [stack_name] --profile [profile_name] --region us-east-1 --template-file csye6225-infra.yml  --parameter-overrides file://parameter.json``` to create stack and start the creation of the resources in aws
* Write command ```aws cloudformation delete-stack --stack-name [stack_name] --profile [profile_name]``` to delete the stack and its resources

## Project Structure
* *csye6225-infra.yml* : YAML CloudFormation file to create vpc, subnets, internet gateways, routes, and route table.
  
## Tech Stack
* AWS CloudFormation
* AWS CLI

## Reference 
* https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-formats.html
