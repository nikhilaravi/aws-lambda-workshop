# Founders and Coders Aws-lambda-workshop

Build a simple version of Twitter using AWS Lambda

###STEP 1
Create an s3 bucket to save messages 

###STEP 2
Create a Lambda Function to save a message to the s3 bucket (you can write this directly into the AWS Lambda console)
If you need - refer to [this repo](https://github.com/nikhilaravi/s3-save) (although it uses promises which you don't need to use!). Save the tweets as json files.
* in the event object you need to specify both the 'message' and the 'bucketName' e.g. 

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

**TEST step 3 has been done correclty by doing a test invocation of the s3 get lambda**

###STEP 4
Create a simple front end with a text input field and a submit button. The submit button should trigger the s3-save lambda. When the page loads trigger the s3-get lambda. 

Useful Reference Repos

* [DWYL Chat](https://github.com/dwyl/chat)
* [s3-save](https://github.com/nikhilaravi/s3-save)
* [s3-get](https://github.com/nikhilaravi/s3-get)
