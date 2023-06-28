Cloud9 deployment

```
aws cloudformation create-stack --stack-name cloud9-<TEAMNAME> --template-body file://cloud9.yml --parameters ParameterKey=TeamName,ParameterValue=<TEAMNAME> --region eu-west-1
```
