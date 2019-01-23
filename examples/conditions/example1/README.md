#Example1: user equal condition with resources and outputs
This examples shows how you can create resources and outputs based on your environment(prod, or test).

##Deploy Product 
sam package --template-file equal.yaml --output-template-file packaged.yaml --s3-bucket shalabi-sam
sam deploy --template-file packaged.yaml --stack-name learn-equal-prod --capabilities CAPABILITY_IAM --parameter-overrides EnvType=prod


##Deploy Test 
sam package --template-file equal.yaml --output-template-file packaged.yaml --s3-bucket shalabi-sam
sam deploy --template-file packaged.yaml --stack-name learn-equal-test --capabilities CAPABILITY_IAM