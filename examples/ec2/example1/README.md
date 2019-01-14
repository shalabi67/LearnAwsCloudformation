#Example 1
shows how to create ec2 instance with a security group and user data.
it shows how to pass the key name as parameter. it alsoe passes the location as parameter.

##Deploy
sam package --template-file ec2-user-data.yaml --output-template-file packaged.yaml --s3-bucket shalabi-sam
sam deploy --template-file packaged.yaml --stack-name learn-ec2-user-data --capabilities CAPABILITY_IAM --parameter-overrides KeyName=learn-main-verginia
