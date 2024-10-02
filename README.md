# High-available-website
Overview

Design and implented a cloud infrastructure that optimizes server efficiency by dynamically shifting requests based on load. This system alsso automates the creation of new servers in the event of a failure, ensuring high availability and reliability.

![Screenshot 2024-10-01 232231](https://github.com/user-attachments/assets/c4280008-ea4a-4503-b950-26ed83b081c2)



Project Detail

AWS Servic Explored:
  •	EC2
	
  •	AMI
	
  •	VPC
	
  •	Security Groups
	
  •	Load Balancer

  •	Autoscaling
 
  •	Target group
	
  •	Template
	
  •	SNS
  
 Step1: To create a Virtual Private Cloud (VPC)
 
     1.	Open the Amazon VPC console.
     
     2.	Select create VPC from the dashboard.
     
     3.	For resources to create, choose VPC and only.
     
     4.	Under the name tag, given the name of VPC
     
     5.	For IPv4 CIDR block, enter an the IPv4 address range for VPC.
     
     6.	Choose the create VPC.
     
 Step2: To create a public subnet.
 
     1.	From the Amazon VPC console.
     
     2.	Select subnet from the side navigation bar.
     
     3.	For VPC ID, select your newly created VPC.
     
     4. For Subnet name, enter a name for your subnet.
     
     5. For Availability zone, select a compatible availability zone.
     
     6. For IPv4 CIDR block, enter 10.0.0.0/24
     
     7.	For IPv4 subnet CIDR block, enter 10.0.0.0/26
     
     8.Click the add subnet button and create other three subnet.

 Step 4. Create Route table.
 
     1. When we create VPC, by default create a route table.
     
     2. For this route table, the name is Hexa-shop route table.
     
 Step 5. Create Internet Gateway
 
     1.	From the Amazon VPC console.
     
     2.	Select Internet Gateway from the side navigation bar.

     3.	Choose create Internet Gateway.
     
     4.	Under the Create internet gateway, enter the name.
     
     5.	Choose Internet Gateway.
     
     6.	Attach your internet Gateway to your VPC.
     
     7.	Under VPC, choose your VPC.

 Step 6. Attach internet gateway and subnets to your route table.
 
     1.	Go to Route Table
     
     2.	Select the Edit Routes.
     
     3.	Add the internet gateway and subnets.


 Step 7. Create Security Group
 
      1.	Under the Basic details, enter the name of security group, description and choose your VPC.
      
      2.	Under the inbound rules, choose SSH, HTTP, HTTPS inbound rules.

 Step 8. Create Ec2 instance
 
     1. Go to the EC2 service in the AWS console. 
     
     2. From the EC2 console dashboard, in the Launch Instance box, choose descriptive name for your instance.
     
     3.	On the launch instance page, under Name and tags, for Name, enter a descriptive name for your instance.  
     
     4.Under Application and OS Images (Amazon Machine Image) select the AMI for Linux Server.
     
     5.Under the instance type, from the instance type list select the hardware configuration for instance. Choose the t2.micro instance type.
     
     6. Under key pair, choose the key pair or create the key pair.
     
     7. Choose Launch Instance.
     
     8. Connect to the instance.
     
     9. Click on connect.

Step 8. On Ec2 instance, deploy a website.

    •	Firstly convert normal user to root user with the help of command
         sudo su –
	 
    •	Update with the help of command yum update.
    
    •	Install httpd with the help of command yum install httpd.
    
    •	Give command for start httpd systemctl start httpd and chkconfig httpd on
    
    •	Choose template from the browser and paste the link address in the server with the command wget (address).
    
    •	Unzip file from zip file.
    
    •	Change directory with the commad cd filename.
    
    •	move the file from source to destination.

 Step 9. To create an AMI
 
     1.Select the instance from which to create the AMI then choose Actions,Images and templates,Create image.
        
     2.On the create image page
     
        •	Under the image name ,enter a unique name for the image.
	
        •	Under the image description,enter an optional description of the image.
	
        •	Click on the check box for No reboot is selected.
	
        •	We tag the AMI and the snapshots with same tags, or you can tag them with different tags.
         
         •	Choose create image.
 Step 10. To create template.
 
     1.Select the instance from which to create the AMI then choose Actions,Images and templates,Create template.   
     
     2.Under the launch template name and description, enter the Launch template name, templatee version description.
     
     3.Choose create template.
  
 Step 11. Create Target Groups
 
     1.	On the Ec2 Console select Target Group from side navigation bar.
     
     2.	Under the basic configuration, choose Instances.
     
     3.	Under the target group name, enter the target group name.
     
     4.	Choose your VPC and choose IP address type.
     
     5.	Choose create target group.

 Step 12. Create Load Balancer.
 
     1.	On Ec2 console, Select Load balancer from side navigation bar.     
     
     2.	Under the basic configuration, enter the load balancer name, choose scheme.
     
     3.	Choose your VPC and select the availability zones.
     
     4.	Choose the security groups and listeners and routing.
     
     5.	Choose create

 Step 13. To Create SNS
 
     1.	Go To AWS SNS console.
     
     2.	Under the details, choose Standard, under the enter the Name.
     
     3.	Choose create topic.
     
     4.	On the SNS console, select subscription from the side navigation bar.
     
     5.	Under the Create subscription, choose the Topic ARN.
     
     6.	Choose the protocol email.
     
     7.	Choose create Subscription.
     
 Step 14. To Create Auto Scaling group
 
     1.	Go to Autoscaling groups console.
     
     2.	Under the launch template, enter the name of autoscaling and choose your template.
     
     3.	Under the network, Choose the subnet.
     
     4.	Under the load balancing, choose attach to an existing load balancer.
     
     5.	Under attach to an existing load balancer, choose from your load balancer.
     
     6.	Enable the elastic load balancing health checks.

     7.	Under the configure group size and scaling, choose the desired capacity.
     
     8. Under a replacement balancer depending on availability requirements, choose No policy.
     
     9.	Choose Next.
     
     10.Choose Next
     
     11. Add tags
