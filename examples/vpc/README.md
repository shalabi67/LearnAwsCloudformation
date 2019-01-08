# VPC
##VPC1 
this is defined in vpc1.png
###Deploy
sam package --template-file vpc-1.yaml --output-template-file packaged.yaml --s3-bucket shalabi-sam
sam deploy --template-file packaged.yaml --stack-name learn-vpc1 --capabilities CAPABILITY_IAM


##VPC2
this is defined in vpc2.png
###Deploy
sam package --template-file vpc-2.yaml --output-template-file packaged.yaml --s3-bucket shalabi-sam
sam deploy --template-file packaged.yaml --stack-name learn-vpc2 --capabilities CAPABILITY_IAM

##VPC with nat gateway

###Deploy
sam package --template-file vpc-natgateway.yaml --output-template-file packaged.yaml --s3-bucket shalabi-sam
sam deploy --template-file packaged.yaml --stack-name learn-vpc-natgateway --capabilities CAPABILITY_IAM
