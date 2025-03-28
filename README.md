# AWS CloudFormation & Lambda Template for IAM User Management  

This project provides an AWS CloudFormation template that automates the creation and management of an IAM user with specific permissions. The template includes an AWS Lambda function that ensures the IAM user is created only if it does not already exist. Additionally, it attaches an IAM policy and generates access keys for the user.  

## **Features**  
- Creates an IAM user (`devops-engineer`) if it does not exist.  
- Attaches an inline IAM policy with permissions for S3 and IAM actions.  
- Generates access keys for the user.  
- Uses AWS Lambda and CloudFormation custom resources for automation.  

## **Architecture Overview**  
- **AWS Lambda Function**: Handles IAM user creation and policy attachment.  
- **IAM Role for Lambda**: Grants necessary permissions for managing IAM resources.  
- **CloudFormation Custom Resource**: Triggers the Lambda function during stack creation.  

## **IAM Permissions**  
The IAM user created by this template receives the following permissions:  
- S3 access (list, create, get)  
- IAM user and policy management permissions  
- Access key creation  

## **Prerequisites**  
- AWS CLI configured with the necessary permissions  
- AWS CloudFormation enabled in your AWS account  

## **Deployment**  
To deploy the CloudFormation stack, use the following AWS CLI command:  

```sh
aws cloudformation create-stack --stack-name iam-user-stack --template-body file://iam-user-template.yaml --capabilities CAPABILITY_NAMED_IAM
