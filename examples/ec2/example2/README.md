#Example 2
Shows how to use CFN-... functuions


##Deploy
sam package --template-file ec2-cfn-init.yaml --output-template-file packaged.yaml --s3-bucket shalabi-sam
sam deploy --template-file packaged.yaml --stack-name learn-ec2-cfn-init --capabilities CAPABILITY_IAM --parameter-overrides KeyName=learn-main-verginia
