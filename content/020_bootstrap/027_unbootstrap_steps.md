---
title: "Unbootstrap Steps"
chapter: false
weight: 27
draft: false
---

## Remove CDK bootstrap

***Purpose***: Remove CDK environment if no longer needed.

If you no longer need to manage resources with the AWS CDK in an environment,
you can "unbootstrap" that environment.

This effectively removes the CDK bootstrap

These are the high-level steps:

{{< step >}}Remove CDKToolkit stack with CloudFormation.{{< /step >}}
{{< step >}}Remove CDK bootstrap bucket.{{< /step >}}

