# hindsight-aws

# Usage

Use CloudFormation to create Hindsight's underlying infrastructure:

```bash
aws cloudformation deploy --stack-name [NAME] --template-file cf/infrastructure.yaml --capabilities CAPABILITY_NAMED_IAM
```

Apply an `iamidentitymapping` to allow users with the `eksUserRole` to work with EKS:

```bash
helm template aws ./helm --set aws.account=[ACCOUNT_ID] | kubectl apply -f -
```
