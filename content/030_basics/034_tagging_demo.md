---
title: "Tagging Demo"
chapter: false
weight: 34
draft: false
---

## Demo: Create CDK resources with tags

As noted in [Tagging AWS resources](https://docs.aws.amazon.com/general/latest/gr/aws_tagging.html),
***tags*** are metadata you can add to your AWS resources to help your resource management:
- automation
- security: access control
- cost and billing
- searching
- organizing

This demonstration builds on the queue demo by adding tags to the Amazon SQS queue resource.

{{% notice note %}}
This demonstration includes steps to copy distinct versions of the `tagging-stack.ts`
file to illustrate certain tagging techniques in the CDK. 
This method was chosen so that those following this demonstration *do not need to type code*,
just copy and paste commands.
This technique is repeated in other demonstrations as well.
{{% /notice %}}

## Tagging Demo Video

{{< youtube rmbX9SqvHhc >}}

## Purpose

Here are the purpose points for 
the [tagging demo deck](https://github.com/bwer432/cultivatecloud/blob/main/tagging-demo/tagging-deck.md).

- ***Why?*** 
  I want to organize cloud resources, track cost allocation, improve automation, and enhance access control.
- ***What?*** 
  Use resource tags on AWS cloud resources.
- ***Where?*** 
  In my AWS account.
- ***How?*** 
  Use AWS CDK to tag resources.
- ***Then…*** 
  I can better manage cloud resources in my AWS accounts.

---

# Use tags on CDK resources

## Purpose: Simplify and enhance cloud resource management

Steps:

{{< step >}}Check for presence of tags on existing CDK deployment.{{< /step >}}
{{< step >}}Add tags in code. (`lib/tagging-stack.ts`).{{< /step >}}
{{< step >}}Re-deploy the CDK app (`cdk deploy`).{{< /step >}}
{{< step >}}Confirm tags.{{< /step >}}
{{< step >}}Use the resources throughout their intended lifecycle.{{< /step >}}

## Add tags to a CDK app definition

```bash
git clone https://github.com/bwer432/cultivatecloud
cd cultivatecloud/tagging-demo/tagging
npm install # repopulate node_modules
npx cdk deploy
vi lib/tagging-stack.ts # show pre-tags baseline
cp ../tagging-stack-direct.ts lib/tagging-stack.ts
npx cdk deploy # then show results and/or source
cp ../tagging-stack-via-map.ts lib/tagging-stack.ts
npx cdk deploy # then show results and/or source
```

## AWS Tagging Documentation

Tagging documentation:
[Tagging AWS resources](https://docs.aws.amazon.com/general/latest/gr/aws_tagging.html)
[Filtering AWS CLI output](https://docs.aws.amazon.com/cli/latest/userguide/cli-usage-filter.html)
