Hosting a website on Amazon EC2 involves several steps, including creating an EC2 instance, configuring security groups, connecting to the instance using Git Bash, and deploying your website code. Here's a step-by-step guide:

Prerequisites:
Amazon Web Services (AWS) Account: Make sure you have an AWS account.

Amazon EC2 Key Pair: Create a key pair to connect to your EC2 instance securely.

Git Bash: Install Git Bash on your local machine if you haven't already.

Step 1: Launch an EC2 Instance
Open the AWS Management Console.
Navigate to the EC2 service.
Click "Launch Instance."
Choose an Amazon Machine Image (AMI), such as Amazon Linux.
Select an instance type and configure other settings as needed.
In the "Configure Security Group" step, add a rule to allow inbound traffic on port 80 (HTTP) and 22 (SSH).
![image](https://github.com/iamnishant22/host_a_website_EC2-AWS/assets/90270425/bfd7117b-74ca-4619-ade4-277bc88ee266)

Launch the instance and select your key pair.
Step 2: Connect to EC2 Instance using Git Bash
Open Git Bash.

Navigate to the directory where your key pair file is stored.

Use the following command to connect to your EC2 instance (replace your-key.pem and your-ec2-ip with your key pair file and EC2 instance IP):

bash
Copy code
ssh -i "your-key.pem" ec2-user@your-ec2-ip
Step 3: Install Required Software on EC2 Instance
Update the package lists:

bash
Copy code
sudo yum update -y
Install a web server (e.g., Apache) and Git:

bash
Copy code
sudo yum install httpd git -y
Start the Apache web server:

bash
Copy code
sudo service httpd start
Ensure that the web server starts on boot:

bash
Copy code
sudo chkconfig httpd on
Step 4: Deploy Your Website Code
Clone your Git repository on the EC2 instance:

bash
Copy code
git clone your-repository-url
Move your website files to the web server directory:

bash
Copy code
sudo mv your-repository-folder/* /var/www/html/
Step 5: Access Your Website
Open your web browser and enter your EC2 instance's public IP address.


Copy code
http://your-ec2-ip
replace your-ec2-ip with your ip ,if not happen with this then http://your-ec2-ip:80

Your website should now be accessible through the public IP address of your EC2 instance.
EXAMPLE WEBSITE:
![s1](https://github.com/iamnishant22/host_a_website_EC2-AWS/assets/90270425/45ae11b0-6ffd-4aae-97f5-4be779c326c3)

