# AWS

> Amazon Web Services

- Wener Vogels is **AWS CTO**


Term | definition
---------- | --------
Scaling in/out | reduce/add nodes(servers)
Scale up/down | add/reduce capacity like RAM, CPUs, etc.
Elasticity | the rubberband effect to expand/contract resources proportionally to the demand.

- Assume everything will fail someday.
- Prevent *single point of failure* by adding backup instances.

## S3

> Simple Storage Service

- it is good for data that does not change fast, because it has a delayed effect to refresh
- stores using **Elastic Block Storage**
- uses **RRS** (Reduced Redundancy Storage) which is less costly
- provides access via REST API and ftp.
- uses Object Storage
- it has a caching effect

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

## Elastic Bean Stalk

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


## ELB
> Elastic Load Balancer

- balances traffic (HTTP, HTTPS, TCP) between EC2 instances using *round-robin*
- scales
- single *CNAME* for DNS config

## CloudWatch

> Monitoring (similar to NewRelic)

- monitoring CPU, Network traffic, etc.
- can set alarms

## RDS

> Relational Database Service

- supports MySQL, Postgres, SQL, Oracle
- quick recovery backups, security, scalability
- monitor with **CloudWacth**
- no *ssh* access or *root* access
- has development mode (way cheaper)

### Access
- you can access it from **EC2** 

`psql -h dev-db.lala.us-east.rds.amazon.com -u admin -p`

## SQS

> Simple Message Queuing Service

- Similar to *RabbitMQ*
- uses a pull (polling) flow

## SWF
> Simple Work Flow

- eg. e-commerce work-flow
- looks like a sequence diagram
- has a **Decider** which decides if should proceed with workflow or abort.
- this can help decouple complex work-flows

## SNS
> Simple Notification Service

- publish messages from app or console
- uses subscribers
- eg. CloudWatch alerts
- uses a push flow

### Supported protocols

- email
- SMS
- SQS
- HTTP
- app json


## Dynamo DB
> NoSQL

- uses **Solid State Drives** (super fast)
- used for stateless apps (eg. sessions)
- the user session state can be saved in NoSQL instead of the client. It wouldn't be possible to keep state in the server when using load balancing.


## IAM
> Identity and Access Management

- recommended for using AWS SDKs
- create a rol for *webserver* and select this role in **AMI**
- that way the EC2 doesn't need to instantiate SDK with creds because it gets them from the EC2 metadata.