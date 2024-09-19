---
title: "Cultivate Cloud"
chapter: true
weight: 1
---

# Cultivate Cloud

Welcome to *CultivateCloud.net*,
a collection of resources to help 
cultivate cloud computing development and deployment.

{{< mermaid >}}
graph TB
cultivatecloudnet(cultivatecloud.net<br>you are here)-->youtubechannel(cultivatecloud<br>YouTube<br>channel)
cultivatecloudnet-->gitrepo(cultivatecloud git repo)
gitrepo2(cultivatecloudsite git repo)-->|builds|cultivatecloudnet
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
class cultivatecloudnet orange;
class youtubechannel blue;
class gitrepo,gitrepo2 green;
class demoA,demoB,demoM,demoN,demoO,demoZ yellow;
{{< /mermaid >}}

## Links

- This [CultivateCloud.net website](https://cultivatecloud.net) provides a launch pad to reach the other components.
- The git repo [`cultivatecloudsite`](https://github.com/bwer432/cultivatecloudsite) is the source code for the cultivatecloud.net website. Most people would not likely clone this unless they wanted a local copy of this commentary.
- The git repo [`cultivatecloud`](https://github.com/bwer432/cultivatecloud) is the repo of demo scripts and CDK app templates. **This is the principal artifact** that most people wanting to follow these demos would clone.
- The [`cultivatecloud` YouTube channel](https://www.youtube.com/channel/UCv3v2LjcRvBntKL1xRe2u_w) provides video commentary on going through some of the demonstrations, and are intended to serve as a baseline of what to expect from those selected demonstrations.

## More

What would *you* like to have demonstrated for AWS cloud resource deployment?

