# Detecting facial details using AWS Rekognition 
This code implements the detection of faces from images stored in an S3 bucket. It is meant to be implemented as a Lambda function on AWS, referring to an Image (file_name) from an S3 bucket (bucket_name) to return key metrics such as emotion, predicted age, and facial positioning. 

## How to deploy and run:
### 1. Creating an S3 Bucket
- You can log in to your AWS Management Console and go to the 'S3' service console
- Click on the "Create bucket" button
- Enter a unique bucket name
- Choose a region
- Click on the "Create bucket" button
### 2. Adding Photos to the S3 Bucket
- Go to your new S3 bucket
- Click on the "Upload" button
- Select the photos you want to upload (you can upload files directly from your desktop) 
- Click on the "Upload" button
### 3. Creating a Lambda Function
- Go to the Lambda service
- Click on the "Create function" button
- Pick a name for your function
- Select a runtime (I selected Python 3.12)
- Leave execution role as 'default' 
- Click"Create function"
### 4. Updating Execution Role Permissions
- Go to the 'configuration' tab of your Lambda function and click the "role name"
- In the newly opened IAM page, click "Add Permissions"
- Add the following permissions: 
- AmazonRekognitionFullAccess (or a custom policy with only read-only permissions)
- AmazonS3ReadOnlyAccess (or a custom policy with only read-only permissions)
### 5. Adding and Running Code from GitHub
- Clone or copy the code from this repo to your lambda function (make sure to point the references to your S3 bucket and picture name!)
- Save/Deploy your code
- Test your function by running it manually or triggering it via an event source (e.g., S3 event).
