# DevOps Demo Project

In this project, I deployed a web application that is written in JAVA on AWS. When deploying this project, I keep note of key concepts in DevOps such as Autoscaling, Containerization, High Availability, CICD, and Infrasctructure as Code.

## Infrastructure
The AWS infrasctruture comprises of AWS services below:
- VPC
- Private Subnets (3)
- Public Subnets (3)
- Route Tables (Public, Private, Default)
- Internet Gateway (1)
- NAT Gateway (1)
- Autoscaling Group
- Launch Template
- EC2
- Security Groups
- Dockerhub
- eu-west-2 region

 All resources packaged and deployed using terraform. In this project, the state file is stored in an s3 bucket `ay-cloud-height-tf-bucket-state`. Most of the resources made use of terraform modules provided by AWS from the terraform documentation.

 ## Autoscaling
 The project contains autoscaling that is configured to monitor cloudwatch metrics for the EC2 instances that will be provisioned. The autoscaling group contains an autoscaling policy that checks if the CPU utilization exceeds 70%. if the previous is true, new instance will be provisioned automatically. And in this instance, it contains a `user_data` that provisions docker and spins up the application.

 ## 

