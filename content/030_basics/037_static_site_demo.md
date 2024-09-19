---
title: "Static Site Demo"
chapter: false
weight: 37
draft: false
---

## Demo: Create an Serverless Static Website

There are several points to this series of demonstrations:
- How to borrow code from other tutorials and demos (and repurpose them).
- Deploying a serverless static website.
- Briefly explaining the deployment of multiple cloud resources in one stack.

## Borrowing

Demonstration of borrowing an AWS CDK app stack template so we don't have to start from scratch. The example will be used in a separate video to create a static website.

{{< youtube HkgRmPG_n8Y >}}

## Deploying

Demonstration of deploying a static website hosted in Amazon S3 fronted by Amazon CloudFront. The demonstration uses the AWS CDK template borrowed in the [prior video](https://youtu.be/HkgRmPG_n8Y).

{{< youtube wv6HhtOVT_Y >}}

## Explaining

Demonstration explaining some of the AWS CDK components for deploying a static website hosted in Amazon S3 fronted by Amazon CloudFront. Includes a brief note on the relationship of the CDK App, Stack, and Construct. The demonstration uses the AWS CDK template [borrowed](https://youtu.be/HkgRmPG_n8Y) and [deployed](https://youtu.be/wv6HhtOVT_Y) earlier.

{{< youtube nm9C9jdZocM >}}

## Purpose

Here are the purpose points for 
the [static site demo deck](https://github.com/bwer432/cultivatecloud/blob/main/static-site-demo/static-site-deck.md).

- ***Why?*** 
  I want to create a serverless static website.
- ***What?*** 
  Use an Amazon S3 bucket and Amazon CloudFront distribution.
- ***Where?*** 
  In my AWS account.
- ***How?*** 
  Use AWS CDK to deploy the bucket, policy, access identity, distribution, certificate, DNS record.
- ***Then…*** 
  I can host a website using Amazon S3.

# Deploy a static website

## Purpose: Show relationships between resources in the stack

Steps:

{{< step >}}Clone AWS Samples example of static site.{{< /step >}}
{{< step >}}Extract that one example for demonstration.{{< /step >}}
{{< step >}}Deploy the static site using CDK *context* values.{{< /step >}}
{{< step >}}Use the static site.{{< /step >}}

## Borrow an example

```bash
git clone https://github.com/bwer432/cultivatecloud
cd cultivatecloud/static-site-demo
git clone https://github.com/aws-samples/aws-cdk-examples
cp -R aws-cdk-examples/typescript/static-site ./static-site
rm -rf aws-cdk-examples
cd static-site
ls
```

## Deploy a static website

```bash
git clone https://github.com/bwer432/cultivatecloud
cd cultivatecloud/static-site-demo/static-site
npm install 
npm run build
accountId=$(aws sts get-caller-identity --query Account --output text)
aws route53 list-hosted-zones --query "HostedZones[].Name"
zone=$(aws route53 list-hosted-zones --query "HostedZones[0].Name" --output text | sed 's@\.$@@')
npx cdk deploy -c accountId=$accountId -c domain=$zone -c subdomain=www
```

## Clean up

Delete the stack when you are done. 
- Redefine the `accountId` and `zone` variables if in a new shell session.
- Use `cdk destroy` with the *same context values* as you used on the `deploy`.

```bash
npx cdk destroy -c accountId=$accountId -c domain=$zone -c subdomain=www -f
```
