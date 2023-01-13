---
title: "AWS Demos"
chapter: true
weight: 1
---

# AWS Demos

Welcome to *AWSdemos.net*,
a collection of resources to help 
cultivate cloud computing development and deployment.

{{< mermaid >}}
graph TB
awsdemosnet(AWSdemos.net<br>you are here)-->youtubechannel(awsdemos<br>YouTube<br>channel)
awsdemosnet-->gitrepo(awsdemo git repo)
gitrepo2(awsdemos git repo)-->|builds|awsdemosnet
youtubechannel-->demoA[SQS queue video]
youtubechannel-->demoB[...]
youtubechannel-->demoM[S3 bucket video]
gitrepo-->demoN[SQS queue demo]
gitrepo-->demoO[...]
gitrepo-->demoZ[S3 bucket demo]
demoN-->|includes|cdkN(CDK app)
demoZ-->|includes|cdkZ(CDK app)

classDef green fill:#9f6,stroke:#333,stroke-width:4px;
classDef orange fill:#f96,stroke:#333,stroke-width:4px;
classDef blue fill:#69f,stroke:#333,stroke-width:4px;
classDef yellow fill:#ff3,stroke:#333,stroke-width:2px;
class awsdemosnet orange;
class youtubechannel blue;
class gitrepo,gitrepo2 green;
class demoA,demoB,demoM,demoN,demoO,demoZ yellow;
{{< /mermaid >}}