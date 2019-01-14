#This provides examples on how to references outputs of othr cloud formation template.
https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/walkthrough-crossstackref.html

##Example1
This example has two templates. the first one creates VPC and exposes a set of outputes, 
while the second one imports these outputs to create an EC2 instance.

this is from https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/walkthrough-crossstackref.html

###Deploy
sam package --template-file vpc.yaml --output-template-file packaged.yaml --s3-bucket shalabi-sam
sam deploy --template-file packaged.yaml --stack-name SampleNetworkCrossStack --capabilities CAPABILITY_IAM

sam package --template-file web.yaml --output-template-file web-packaged.yaml --s3-bucket shalabi-sam
sam deploy --template-file web-packaged.yaml --stack-name SampleWebAppCrossStack --capabilities CAPABILITY_IAM

###files
####vpc.yaml
this file will create a vpc.
#####notice on the output section how it export resources so they can be used by other cloudformation template

####web.yaml
this file create an ec2 instance which uses a security group and subnet defined on vpc.yaml.
