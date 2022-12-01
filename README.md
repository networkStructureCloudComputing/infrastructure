# Infrastructure
``CloudFormation - AWS``

## About the project
Created an vpc, subnets, internet gateway, routes, security group, EC2 instance, and route table using aws cloudformation

## How To Run
* Install and configure AWS Command Line Interface (CLI) on your development machine (laptop) from AWS Website.
* Create AWS CLI user profiles in dev and demo account. Create secret key and download the csv file.
* Create dev profile for your dev AWS account and demo profile for your production AWS account.
* Both dev and demo AWS CLI profiles should be set to use the ``us-east-1`` region or the region closest to you.
* Clone the repository into your local machine using git clone command.
* Go to your project folder using cd
* Make a ``parameter.json`` file for configuration of the infra in which you want to build all your resources.
* Set ``export AWS_PROFILE=demo`` or it can be any environment of your choice  
* Set ``export AWS_REGION=us-east-1`` or it can be any region of your choice

* Write command ```aws cloudformation create-stack --stack-name [stack name] --template-body file://csye6225-infra.yml --parameters file://parameter.json --capabilities CAPABILITY_NAMED_IAM``` to create stack and start the creation of the resources in aws
* Write command ```aws cloudformation update-stack --stack-name [stack name] --template-body file://csye6225-infra.yml --parameters file://parameter.json --capabilities CAPABILITY_NAMED_IAM``` to update exit stack and its resources
* Write command ```aws cloudformation delete-stack --stack-name [stack name] ``` to delete the stack and its resources
* Write command ```aws s3 rm s3://bucket-name --recursive``` to delete data from s3
* Write command ```aws --profile productionAdmin acm import-certificate --certificate fileb://certificate.crt  --certificate-chain fileb://ca_bundle.crt  --private-key fileb://private.key``` to import certificate


## Project Structure
* *csye6225-infra.yml* : It has it's logic to create vpc, subnets, internet gateways, routes, route table,security group, Db security group, S3, RDS instance, IAM Role, Policy, EC2 instance, userData, and attachment.
  
## Teach Stack
* AWS CloudFormation
* AWS CLI

## Features
* Create, Update, and Delete stack and its resources(RDS, S3, EC2, Route53, etc) using cloud formation
