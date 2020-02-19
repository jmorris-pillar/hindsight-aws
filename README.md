# hindsight-aws

# Usage

Use CloudFormation to create Hindsight's underlying infrastructure. Please override the 
`RdsPassword` parameter value for your own security's sake.

```bash
aws cloudformation deploy \
  --stack-name [NAME] \
  --template-file hindsight.yaml \
  --capabilities CAPABILITY_NAMED_IAM \
  --parameter-overrides RdsPassword=5bcfd3fb5cba35da5f1be3c347bc
```

Apply an `iamidentitymapping` to allow users with the `eksUserRole` to work with EKS:

```bash
helm template aws ./helm --set aws.account=[ACCOUNT_ID] | kubectl apply -f -
```
