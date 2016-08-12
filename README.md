# Founders and Coders Aws-lambda-workshop

Build a simple version of Twitter using AWS Lambda

###STEP 1
Create an s3 bucket to save messages 

###STEP 2
Create a Lambda Function to save a message to the s3 bucket (you can write this directly into the AWS Lambda console)
If you need - refer to [this repo](https://github.com/nikhilaravi/s3-save) (although it uses promises which you don't need to use!). Save the tweets as json files.
* in the event object you need to specify both the 'message' and the 'bucketName' e.g. 
* make sure the lambda has the correct role and permissions to save to s3

```
{
  message: 'my first tweet',
  bucketName: 'twitter-db'
}
```

**TEST steps 1 and 2 have been done correclty by doing a test invocation of the s3 save lambda function in the AWS console using a test event object. Create a  Check the s3 bucket to see if the tweet has been saved**

###STEP 3
Create a Lambda function to retrieve messages from an s3 bucket
* in the event object you need to specify the 'bucketName'
* remember you need to first list all the objects in the folder and then get the contents of each file
* make sure the lambda has the correct role and permissions to read from s3

**TEST step 3 has been done correclty by doing a test invocation of the s3 get lambda**

MAKE SURE STEPS 1, 2, and 3 work!! Then move on to step 4 if you have time!

###STEP 4
Create two endpoints on the api gateway:
* `/savemessage`
* `/getmessage`

Then 
* Connect the `/savemessage` endpoint to the `s3-save` lambda
* Connect the `/getmessage` endpoint to the `s3-get` lambda

Get your API invoke URL!

###STEP 4
Create a simple front end with a text input field and a submit button. The submit button should trigger the s3-save lambda.
When the page loads trigger the s3-get lambda. 

Useful References

* [DWYL Chat app](https://github.com/dwyl/chat)
* [s3-save lambda](https://github.com/nikhilaravi/s3-save)
* [s3-get lambda](https://github.com/nikhilaravi/s3-get)

* [Node.js AWS SDK reference](https://aws.amazon.com/sdk-for-node-js/)
