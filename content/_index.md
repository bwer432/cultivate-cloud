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

## Links

- This [AWSdemos.net website](https://www.awsdemos.net) provides a launch pad to reach the other components.
- The git repo [`awsdemos`](https://github.com/bwer432/awsdemos) (*plural*) is the source code for the awsdemos.net website. Most people would not likely clone this unless they wanted a local copy of this commentary.
- The git repo [`awsdemo`](https://github.com/bwer432/awsdemo) (*singular*) is the repo of demo scripts and CDK app templates. **This is the principal artifact** that most people wanting to follow these demos would clone.
- The [`awsdemos` YouTube channel](https://www.youtube.com/channel/UCv3v2LjcRvBntKL1xRe2u_w) provides video commentary on going through some of the demonstrations, and are intended to serve as a baseline of what to expect from those selected demonstrations.

## More

What would *you* like to have demonstrated for AWS cloud resource deployment?

