# AWS-S3-Task
## Configuring and setting up s3 cli
1. The first order of business is to set up an AWS EC2 instance. This will use both the port 80 as well as a simple ssh port and IP.
2. You must then ssh in with `ssh -i (pem file) ubuntu@(iPv4 DNS)`. Then update and upgrade your system.
3. You then need to install some prerequisites which include; `sudo apt-get install python` and `sudo apt-get install python-pip` and `sudo apt-get install awscli`.
4. Then simply type `aws configure`, enter you keys, then use the required region (in my case `eu-west-1`) and json as the output format.
5. You can finally make a bucket, in order to make one type `aws s3 mb s3://(bucket-name)`.
6. After this you can enter copy a file over after making one by using `aws s3 cp <file name> s://(bucket-name)`.
7. To change the file permissions click the file and go to the permissions tab, then select all the read options.

## CRUD commands
- `rm -rf devops_bootcamp_test.text` to remove a file
- `aws s3 sync s3://[bucket name]/ [file name]` this will bring everything down (download) from your bucket so your local host is up to date
- `aws s3 rm s3://[bucket name]/[file name]` delete the file from the bucket
- Doing the above command your file won't exist in your bucket, go to aws and refresh buckets, you will see file is not there
- `aws s3 rb s3://[bucket name]/[file name]` - rb means remove bucket, doing this your bucket will no longer exist
  
## s3 Glaciers
A service that accounts for non-frequently used data, which helps to save on cost as files or buckets that don't need to be accessed frequently can be kept in the s3 glacier. So they exist but just put to one side. If someone does need to access it notification has to be given.
