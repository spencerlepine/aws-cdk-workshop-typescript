# AWS CDK TypeScript Workshop Project

Hello world project for the  **Introduction to the AWS CDK - [Workshop](https://cdkworkshop.com)**

The deployable application is an API endpoint connected to lambda functions, which interact with a simple DynamoDB database to track endpoint request hits.

Date: October 22nd, 2022.

## What is AWS CDK?

> AWS Cloud Development Kit (CDK) is an open-source software development framework used to model and provision your cloud application resources with familiar programming languages.

Instead of manually deploying/provisioning different AWS services is the browser say, use infrastructure as code to take care of this. This defines what to services to deploy, how they communicate, and what permissions they need.

You can write Javascript to define the infrastructure, or even use for loops. This will generate a `.yml` configuration file under the hood before deploying, but this is a much better approach at scale instead of digging through/updating `yaml` files.

## Useful commands

* `npm run build`   compile typescript to js
* `npm run watch`   watch for changes and compile
* `npm run test`    perform the jest unit tests
* `cdk deploy`      deploy this stack to your default AWS account/region
* `cdk diff`        compare deployed stack with current state
* `cdk synth`       emits the synthesized CloudFormation template

## Deployment Notes

If you were to run `cdk deploy`, it will create the resources, the `CloudStack`, `CloudWatch` logs, and `S3 Buckets`.

Running `cdk destroy` removes the resources.

> **Note (a):** After `cdk destroy`, the Lambda function created will generate CloudWatch logs that are permanently retained. These will not be tracked by CloudFormation since they are not part of the stack, so the logs will still persist. You will have to manually delete these in the console if desired.

> **Note (b):** The bootstrapping stack created through `cdk bootstrap` command still exists. If you plan on using the CDK in the future (we hope you do!) do not delete this stack. If you would like to delete this stack, it will have to be done through the CloudFormation console. Head over to the CloudFormation console and delete the CDKToolkit stack. The S3 bucket created will be retained by default, so if you want to avoid any unexpected charges, be sure to head to the S3 console and empty + delete the bucket generated from bootstrapping.