# Introduction
This is a Serverless.js template to build a backend for a chat web application.  The stack includes:
* S3 Website Bucket
* CloudFront CDN
* DNS Record for CloudFront
* Cognito User Pool, App Client and Identity Pool
* DynamoDB tables
* AppSync GraphQL implementation
* IAM roles and policies


# Installation
* Clone this repository
* yarn install
* Make sure serverless framework is installed globally
* edit the `custom` section of YML file with 4 values:
  * AWS account id
  * domain name (see below)
  * website name (see below)
  * SSL certificate ARN (see below)
* sls deploy --stage dev


### Cognito
* THERE ARE 2 MANUAL STEPS FOR COGNITO
  * You must set the email verification type to link
  * You must set Cognito as a provider for your app client
  * You must set the domain name for the authentication server (use website name, replace `.` with `-`)
  
### CDN/Website
* This project assumes that you have a domain on AWS. If you do not,
  * You should create an SSL certificate on ACM
  * You will need to create an alias for the CloudFront domain to the website bucket name
* Wait approx 25 minutes for CloudFront to complete
* Wait approx 30 more minutes for DNS record to propagate


* Install the front end react client


# Usage
Start by registering with an email.  Cognito will send you a verification link, which you must accept.
Return to the login screen and enter your credentials.
You can register 2 accounts and have 2 windows open to test the chat
Refresh the user list and start a chat.
