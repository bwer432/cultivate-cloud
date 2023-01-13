---
title: "Unbootstrap Script"
chapter: false
weight: 28
draft: false
---

## Unbootstrap AWS CDK

Here is an example script to accomplish the removal of a CDK bootstrap.

{{< step >}}In AWS CloudShell, perform the following commands.{{< /step >}}

```bash
aws cloudformation list-stacks --query "StackSummaries[?StackName=='CDKToolkit'&&StackStatus=='CREATE_COMPLETE']"
aws cloudformation delete-stack --stack-name CDKToolkit
cdkbucket=$(aws s3 ls | grep cdk- | awk '{printf $3}')
echo $cdkbucket
aws s3api delete-objects --bucket $cdkbucket \ 
  --delete "$(aws s3api list-object-versions \
  --bucket $cdkbucket \
  --output=json \
  --query='{Objects: Versions[].{Key:Key,VersionId:VersionId}}')"
aws s3api delete-bucket --bucket $cdkbucket
```

{{% notice note %}}
If there are no versions of objects in the bucket to delete, 
you may receive an error on the `delete-objects` step. 
That should be benign. 
Continue with the `delete-bucket` operation.
{{% /notice %}}

## Unbootstrap Video

{{< youtube yUst8FdAgy4 >}}

