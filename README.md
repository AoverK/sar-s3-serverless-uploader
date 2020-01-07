# Serverless S3 Uploader

The Serverless S3 Uploader allows you to upload TXT files to Amazon S3 buckets from your web applications using pre-signed URLs.

Important: this application uses various AWS services and there are costs associated with these services after the Free Tier usage - please see the [AWS  pricing page](https://aws.amazon.com/pricing/) for details.

```bash
.
├── README.MD                   <-- This instructions file
├── s3UploaderFunction          <-- Source code for the main lambda function
│   └── app.js                  <-- Main Lambda handler
│   └── testHarness.js          <-- For testing code locally
│   └── package.json            <-- NodeJS dependencies and scripts
├── template.yaml               <-- SAM template
```

## Requirements

If using outside of the AWS Serverless Application Repository:

* AWS CLI already configured with Administrator permission
* [NodeJS 12.x installed](https://nodejs.org/en/download/)

## Installation Instructions

1. [Create an AWS account](https://portal.aws.amazon.com/gp/aws/developer/registration/index.html) if you do not already have one and login.
1. Go to the app's page on the [Serverless Application Repository](https://serverlessrepo.aws.amazon.com/applications/) and click "Deploy"

## Using this Application

* This application creates an API Gateway endpoint where your application can request a pre-signed URL to upload TXT objects to an S3 bucket. Once the API returns the URL, your application can PUT the object data to this URL to complete the upload.
* This application is for educational purposes and does not provide any throttling on the API Gateway endpoint. For production usage, you should [apply throttling to your API resources](https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-request-throttling.html).
* You can modify this application to upload other types of object.

## How it works

* Deploy this serverless application and take a note of the API endpoint.
* Invoke the API to receive a pre-signed URL for uploading a TXT file. Use this pre-signed URL to complete the upload.
* For a live example of this, see [this Fiddle](https://jsfiddle.net/jbeswick/Lq3vkdx2/). View the browser console to see logs of how the Fiddle is interacting with the API Gateway and presigned URL.

==============================================

Copyright 2019 Amazon.com, Inc. or its affiliates. All Rights Reserved.

SPDX-License-Identifier: MIT-0
