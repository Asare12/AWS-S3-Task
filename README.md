# AWS-S3-Task
## How to create an ec2 instance
1. Login to AWS and enter the EC2 Page 2 .Press Launch Instance button
2. Select your AMI, for this example select Ubuntu Server 16.04 LTS (HVM), SSD Volume Type and then move to the next step
3. Choose your instance type, for this example select t2 micro and then move to the next step
4 .Select your preferred Network
5. Select your preferred Subnet
6. Set auto assigne public IP to Enable and move onto the next step
7. Leave storage as it is, and move onto the next step
8. Add a tag, with the desired name of your instance, and move onto the next step
9. Change the name of the security group to your desiered name
10. Set the source of the first rule to: My IP
11. Create a new rule and set the Type to HTTP, then set the Source to Anywhere
12. Create a new rule, leaving the Type as default, then set the Port Range to 3000, then move onto the next step.
13. Place a new, or existing security group .pem file into your .ssh file (c/users/name/.shh)
14. Select that file as your security group key pair
15. Finish instance creation


## Starting the node application with your EC2 Instance
1. After creating your EC2 instance, copy the app folder to the virtual machine, to do this use: scp -i [.pem file] -r [app location path] ubuntu@[remote client]:[remote location path] This will copy the files over, make sure to be in your ssh folder when you run this.
2. Run a provision file containing the commands required to install nodejs, this will contain the following commands:
3. In order to ssh into the remote virutal machine, use ssh -i devop_bootcamp.pem ubuntu@[remote client], from there you can use the virutal machine.
4. You can now run the application as normal by using cd app and then node app.js. You should be able to access the Port 3000 page by using your public IP (available by accessing Connect to instance -> EC2 Instance connect on the instance page.

## Configuring and setting up s3 cli
1. The first order of business is to set up an AWS EC2 instance. This will use both the port 80 as well as a simple ssh port and IP.
2. You must then ssh in with ssh -i (pem file) ubuntu@(iPv4 DNS). Then update and upgrade your system.
3. You then need to install some prerequisites which include; sudo apt-get install python and sudo apt-get install python-pip and sudo apt-get install awscli.
4. Then simply type aws configure, enter you keys, then use the required region (in my case eu-west-1) and json as the output format.
5. You can finally make a bucket, in order to make one type aws s3 mb s3://(bucket-name).
6. After this you can enter copy a file over after making one by using aws s3 cp <file name> s://(bucket-name).
7. To change the file permissions click the file and go to the permissions tab, then select all the read options.
  
  
