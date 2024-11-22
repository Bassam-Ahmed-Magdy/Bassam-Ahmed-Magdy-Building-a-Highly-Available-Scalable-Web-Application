# Bassam-Ahmed-Magdy-Building-a-Highly-Available-Scalable-Web-Application
Project Documentation: Building 
a Highly Available, Scalable 
Web Application
Supervised by : DR . Ahmed El-Hamy
Name: Bassam Ahmed Magdy Mohamed
Student Number : 21050513
Table of Contents
1. Introduction
2. Phase 1: Planning and Design
o 1.1 Architectural Diagram
o 1.2 Cost Estimation
3. Phase 2: Creating a Basic Functional Web Application
o 2.1 Virtual Private Cloud (VPC)
o 2.2 EC2 Instance
o 2.3 Testing the Web Application
4. Phase 3: Decoupling the Application Components
o 3.1 Updating VPC Configuration
o 3.2 Setting up Amazon RDS
o 3.3 Secrets Management and Database Migration
5. Phase 4: Implementing High Availability and Scalability
o 4.1 Application Load Balancer
o 4.2 EC2 Auto Scaling
Introduction
This documentation outlines the step-by-step process for designing, deploying, and 
scaling a web application using AWS services. The project follows a structured 
approach that includes planning the architecture, setting up a basic web application, 
decoupling its components for better management, and implementing high availability 
and scalability.
Phase 1: Planning and Design
1.1 Architectural Diagram
1.2 Cost Estimation
1. Open AWS Pricing Calculator:
2. Estimate the Costs:
o Add EC2, RDS, VPC, and Load Balancer services based on the 
architecture and calculate 12-month costs.
AWS Components (Services) Used
1. Amazon VPC (Virtual Private Cloud):
To create a virtual network with public and private subnets to isolate 
different parts of the infrastructure (web servers and databases).
2. Amazon EC2 (Elastic Compute Cloud):
Hosts the web application on virtual machines (EC2 instances) running 
Ubuntu.
3. Amazon RDS (Relational Database Service):
Hosts the MySQL database in a private subnet for the application, 
improving security and managing the database more efficiently.
4. Amazon Secrets Manager:
Stores and manages sensitive credentials (e.g., database credentials) 
securely.
5. Elastic Load Balancing (Application Load Balancer):
Distributes incoming traffic across multiple EC2 instances to ensure 
high availability and load balancing.
6. Amazon EC2 Auto Scaling:
Automatically adjusts the number of EC2 instances based on traffic 
demands, ensuring scalability.
7. AWS IAM (Identity and Access Management):
Controls permissions for the EC2 instances to access AWS services 
securely, like Secrets Manager.
8. AWS Cloud9
Provides a cloud-based development environment for managing and deploying 
code.
Phase 2: Creating a Basic Functional Web 
Application
2.1 Virtual Private Cloud (VPC)
1. Create a VPC:
o Create a new VPC with a CIDR block (10.0.0.0/16).
2. Create Subnets:
o Create a public subnet (10.0.0.0/24) and a private subnet (10.0.2.0/24).
3. Set up Internet Gateway and Route Tables:
o Attach an Internet Gateway to the VPC and configure the public subnet 
route table to route internet traffic.
2.2 EC2 Instance
1. Launch EC2 Instance:
o Navigate to the EC2 dashboard, select an Amazon Ubuntu AMI, and 
launch a t2.micro instance in the public subnet.
2. Configure Security Group:
o Allow HTTP (port 80) and SSH (port 22) traffic.
2.3 Testing the Web Application
1. Retrieve Public IP:
o Get the public IP of the EC2 instance from the AWS console.
2. Test the Application:
o Open the web app in a browser and test 
Phase 3: Decoupling the Application Components
3.1 Updating VPC Configuration
1. Create Additional Subnets:
o Create private subnets across different availability zones.
2. Update Route Tables:
o Ensure internal communication is enabled between subnets.
3.2 Setting up Amazon RDS
1. Create an RDS Database:
o Create a MySQL database using RDS in the private subnet and disable 
public access.
2. Configure Security:
o Set up a security group to allow access only from the EC2 instance.
3.3 Secrets Management and Database Migration
1. Store Credentials in Secrets Manager:
o Securely store MySQL database credentials using AWS Secrets 
Manager.
2. Migrate Data to RDS:
Phase 4: Implementing High Availability and 
Scalability
4.1 Application Load Balancer
1. Create a Load Balancer:
o Set up an Application Load Balancer.
2. Configure HTTP Listener:
o Add a listener on port 80 for web traffic.
4.2 EC2 Auto Scaling
1. Create a Launch Template:
o Create a launch template for the web application in EC2.
2. Create Auto Scaling Group:
o Attach the launch template to the Auto Scaling group and configure it 
for multiple availability zones.
Conclusion
This project demonstrated the successful design and deployment of a highly 
available, scalable web application using AWS services. By following a 
structured approach, we started with creating a functional web application and 
progressively enhanced its architecture to ensure high availability, security, 
and scalability. Through the use of services like Amazon VPC, EC2, RDS, and 
Auto Scaling, we achieved a resilient and cost-effective solution capable of 
handling varying traffic loads. This project serves as a practical example of 
how cloud technologies can be utilized to build modern, scalable web 
applications with minimal downtime and optimal performance.
