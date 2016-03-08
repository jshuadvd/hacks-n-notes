# Elastic BeanStack


> Platform as a Service

- Similar to Heroku, but more configurable
- supports NodeJS
- Server logs to *S3*
- Manages capacity, load-balancing, etc.
- Uses *git* to deploy
- uses micro *EC2* Amazon Linux *AMI*
- Auto scaling
- container based
- can be used for *smoke tests*

## How to deploy to EBS using CircleCI

### Configure AWS
1. Create an *EBS* environment using the dashboard.
1. Save the EBS configuration using the dashboard.
1. Create an *IAM* user for *CircleCI* with full permissions for *EBS*.
1. Set the AWS credentials for that user in CircleCI's **Project Settings > AWS Credentials**.

### Init eb

1. `eb init` in the repo.
1. Do not commit the *.gitignore* changes from `eb init`.
1. `git commit` the *.elasticbeanstack* directory with the config file.

### Configure circle.yml

Add the awsebcli dependency:

```yaml
dependencies:
  pre:
    - sudo pip install awsebcli
```

Add the deployment config:
```yaml
deployment:
  production:
    branch: master
    commands:
      - git add build/ # add to git staging all the build files you want to include in tarball
      - eb deploy --staged # create & deploy the tarball with the last git commit and staged files
```