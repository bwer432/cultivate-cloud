---
title: "Bootstrap Script"
chapter: false
weight: 23
draft: false
---

## Bootstrap AWS CDK

If you simply use the command:

```bash
cdk bootstrap
```

in an unbootstrapped environment, 
you would likely receive an error such as:

> Specify an environment name like 'aws://123456789012/us-east-1', or run in a directory with 'cdk.json'.

## Environment = Account + Region

A CDK ***environment*** consists of an **AWS account** + **AWS region**
which you have *bootstrapped* to allow using the CDK to deploy resources.

{{< mermaid >}}
graph TB
subgraph env[CDK Environment]
  account((AWS Account))
  region((AWS Region))
end
{{< /mermaid >}}

Therefore, you could provide the `cdk bootstrap` command with 
the path of the environment in which you wish to deploy resources.

{{< step >}}In AWS CloudShell, perform the following commands.{{< /step >}}

```bash
AWS_ACCOUNT_ID=$(aws sts get-caller-identity --query Account --output text)
echo $AWS_ACCOUNT_ID 
echo $AWS_REGION
echo aws://$AWS_ACCOUNT_ID/$AWS_REGION
cdk bootstrap aws://$AWS_ACCOUNT_ID/$AWS_REGION  
```

{{% notice note %}}
How was the value of `AWS_REGION` chosen by AWS CloudShell?
{{% /notice %}}

{{% expand "Reveal answer" %}}
AWS CloudShell uses the region you had selected in the AWS Console.
{{% /expand %}}


