#Custom Resources Walkthrough
This is from the aws walkthrough: 
https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/walkthrough-custom-resources-lambda-lookup-amiids.html

#Deploy
##1- Upload lambda code to s3 
1- upload zip files to shalabi-sam bucket.

##2- Deploy lambda function
sam package --template-file lambda.yaml --output-template-file lambda-packaged.yaml --s3-bucket shalabi-sam
sam deploy --template-file lambda-packaged.yaml --stack-name learn-custom-resources-lambda --capabilities CAPABILITY_IAM --parameter-overrides S3Bucket=shalabi-sam

##3- create instance using custom resource
sam package --template-file example.yaml --output-template-file example-packaged.yaml --s3-bucket shalabi-sam
sam deploy --template-file example-packaged.yaml --stack-name learn-custom-resources-example --capabilities CAPABILITY_IAM

