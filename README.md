# AWS-playground

step -1: enable mfa for root user

Step 0: enable cloudtrail (and allow it to create a bucket for logs)
<br>step 0.1: enable log file validation
<br>step 0.2: figure out how to enable aws kms
<br>step 0.3: events - select 'management events' only for free tier

step 0.A: go to aws billing & cost management and set up a budget for cost alerts

Step 1: create an admin security group with 'AdministratorAccess' enabled

Step 2: create an admin account for myself inside 
<br>step 2.1: provide user access to the aws management console
<br>step 2.2: i want to create an iam user
<br>step 2.3: add user to admin group

step 3: create iam role so it can access s3 without session token
<br>step 3.1: choose trusted entity 'AWS Service'
<br>step 3.2: use case 'ec2' and ec2 all aws services
<br>step 3.3: permission policies choose 'AmazonS3FullAccess'

step 4: create ec2
<br>step 4.1: disable ssh
<br>step 4.2: continue without a key pair
<br>step 4.3: iam role - s3 bucket access role 
<br>step 4.s3: create bucket
<br>step 4.s3.1: ACls disabled
<br>step 4.s3.2: block all public access

step 5: fleet manager - configure DHMC
<br>step 5.1: enable DHMC
<br>step 5.2: create AWSSystemsManagerDefaultEC2InstanceManagementRole

step 6: session manager - start session - select target instance - launch

step 7: console
<br>step 7.1: sudo useradd username
<br>step 7.2: sudo passwd username
<br>step 7.3: su username
<br>step 7.4: pwd and make sure you are in home/username or else you will have no folder permissions
<br>step 7.5: use cd ~ to access /home/username
<br>step 7.6: echo 'hi this is a nice' > test.txt
<br>step 7.7: aws s3 ls (prints buckets)
<br>step 7.8: aws s3 cp test.txt s3://bucketname   (copy to bucket)
<br>step 7.9: aws s3 cp s3://bucketname/test.txt test.txt   (down from bucket)
