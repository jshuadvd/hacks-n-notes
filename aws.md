# AWS

> Amazon Web Services

- Wener Vogels is AWS CTO


Term | definition
---------- | --------
Scaling in/out | reduce/add nodes(servers)
Scale up/down | add/reduce capacity like RAM, CPUs, etc.
Elasticity | the rubberband effect to expand/contract resources proportionally to the demand.

- Assume everything will fail someday.
- Prevent *single point of failure* by adding backup instances.

## S3

> Simple Storage Service

- it has a caching effect
- it is ogod for data that does not change fast, because it has a delayed effect to refresh
- stores **Elastic Block Storage**
- uses RRS (Reduced Redundancy Storage) which is less costly
- provides access via REST API and ftp.
- uses Object Storage

### Object Storage

- stores in flat organization containers called **buckets**
- object retrieval by keys
- by keeping it flat, it is very fast to query

## Glacier

- like **S3** but for archiving
- 3 to 5 hour retrieval time
- super cheap
- use it for backups 
- uses Object Storage

## CloudFront

> Content Delivery Network (CDN)

- uses Object Storage

## Elastic Bean Stack

> Platform as a Service

- Similar to Heroku, but more configurable
- supports NodeJS
- Server logs to **S3**
- Manages capacity, load-balancing, etc.
- Uses *git* to deploy
- uses micro **EC2** Amazon Linux **AMI**
- Auto scaling
- container based
- can be used for *smoke tests*

## CloudFormation

> Templates for **AWS** environments

- text template files of your AWS environment written in json
- can pass parameters
- this would be helpful to create an instance of certain environment, for example *staging* environment for QA.

## CloudFormer

> helps you to create a **CloudFormation** template





