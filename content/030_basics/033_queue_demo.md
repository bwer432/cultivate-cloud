---
title: "Queue Demo"
chapter: false
weight: 33
draft: false
---

## Demo: Create an Amazon SQS Queue

As noted in [The AWS Blog by Jeff Barr in 2009](https://aws.amazon.com/blogs/aws/aws-blog-the-first-five-years/),
the [Amazon Simple Queue Service (SQS) was the first AWS service released](https://aws.amazon.com/blogs/aws/amazon_simple_q/).

This queue demo could be demonstrated in (at least) two ways:
- from scratch
- from the `awsdemo` repo

The former includes examples of AWS CLI commands for sending and receiving messages.
The latter includes examples of using Python code and the `boto3` AWS SDK for Python to send and receive messages.

## From Scratch

{{< youtube blnjyseXQVo >}}

## From the `awsdemo` repo

{{< youtube v6p1yVHuZ0M >}}

## Purpose

Here are the purpose points for 
the [queue demo deck](https://github.com/bwer432/awsdemo/blob/main/queue-demo/queue-deck.md).

- ***Why?*** 
  I want to use a message queue in the AWS cloud.
- ***What?*** 
  Use an AWS CDK environment.
- ***Where?*** 
  In my AWS account.
- ***How?*** 
  Use AWS CDK to create an Amazon SQS Queue.
- ***Then…*** 
  I can send and receive messages via a message queue in my AWS account.

## Purpose: Create a CDK stack with a queue

Steps:

{{< step >}}Create a CDK app (`cdk init`).{{< /step >}}
{{< step >}}Uncomment the Amazon SQS bits (`vi lib/queue-stack.ts`).{{< /step >}}
{{< step >}}Deploy the CDK app (`cdk deploy`).{{< /step >}}
{{< step >}}Send and receive queue messages.{{< /step >}}
{{< step >}}Remove the CDK app (`cdk destroy`).{{< /step >}}

---

## Deploy a queue via CDK app stack

```bash
mkdir queue
cd queue
cdk init app --language=typescript
cdk deploy
aws sqs list-queues 
q=$(aws sqs list-queues --query "QueueUrls[0]" --output text)
aws sqs receive-message --queue-url $q --wait-time-seconds 20
aws sqs send-message --queue-url $q --message-body "hello, world" 
cdk destroy --force
```

## Amazon SQS Documentation

Queue code examples:
- [Amazon SQS boto3 API](https://boto3.amazonaws.com/v1/documentation/api/latest/guide/sqs-example-sending-receiving-msgs.html)
- [Amazon SQS Python3 SQS code examples](https://docs.aws.amazon.com/code-library/latest/ug/python_3_sqs_code_examples.html)

## Deploy a queue via CDK app stack with Python clients

```bash
git clone https://github.com/bwer432/awsdemo
cd awsdemo/queue-demo/queue
npm install # repopulate node_modules
npx cdk deploy
aws sqs list-queues 
q=$(aws sqs list-queues --query QueueUrls --output text | grep QueueStack-QueueQueue)
aws sqs receive-message --queue-url $q --wait-time-seconds 20
aws sqs send-message --queue-url $q --message-body "hello, world" 
python3 ../sqs-send.py $q
python3 ../sqs-recv.py $q
npx cdk destroy --force
```
