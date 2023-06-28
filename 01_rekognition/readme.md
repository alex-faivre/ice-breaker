# ipi ONBOARDING REKOGNITION WORKSHOP

## Before you start, make sure you install:
- Serverless framework:  `npm install -g serverless`

- aws-cli: https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html 


## Steps to deploy:

1/ deploy stack

`serverless deploy --stage teamname_in_lowercase`

2/ Download the 'index.html' file and Replace the API_GATEWAY_URL variable with the generated API gateway url from deployed stack

3/ Upload the 'index.html' file in your website bucket

4/ Verify you static web page



