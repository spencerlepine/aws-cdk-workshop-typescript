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
