---
title: "Empty Stack"
chapter: false
weight: 32
draft: false
---

## Demo: Use an AWS CDK Environment

Prior to deploying useful resources such as queues, buckets, and functions, 
it can be useful to practice the procedure for deploying *anything* using the CDK.

The "empty" demo creates a CloudFormation stack with no resources other than some CDK metadata.

{{< youtube MszIsHI2N8M >}}

Here are the purpose points for 
the [empty demo deck](https://github.com/bwer432/cultivatecloud/blob/main/empty-demo/empty-deck.md).

- ***Why?*** 
  I want to practice resource deployment in the AWS cloud.
- ***What?*** 
  Use an AWS CDK environment.
- ***Where?*** 
  In my AWS account.
- ***How?*** 
  Use AWS CDK to create an AWS CloudFormation stack, then delete it.
- ***Then…*** 
  I know how to use AWS CDK to deploy and destroy AWS resources in my account(s).


## Purpose: Deploy an empty stack

Steps:

{{< step >}}Create a CDK app (`cdk init`).{{< /step >}}
{{< step >}}Deploy the CDK app (`cdk deploy`).{{< /step >}}
{{< step >}}*Use the cloud app resources*.{{< /step >}}
{{< step >}}Remove the CDK app (`cdk destroy`).{{< /step >}}

## Deploy an "empty" CDK app stack

```bash
mkdir empty
cd empty
cdk init app --language=typescript
cdk deploy
cdk destroy
```
