# Deploying 2048 Game App on Amazon EKS

Prerequisites:

EC2 instance for the setup

Terraform for infrastructure provisioning.

kubectl – A command line tool for working with Kubernetes clusters. For more information, see Installing or updating kubectl.

AWS CLI – A command line tool for working with AWS services, including Amazon EKS. For more information, see Installing, updating, and uninstalling the AWS CLI in the AWS Command Line Interface User Guide. After installing the AWS CLI, we recommend that you also configure it. For more information, see Quick configuration with aws configure in the AWS Command Line Interface User Guide.

# Project Description:

A Kubernetes End-to-End (E2E) project for deploying a 2048 game app on Amazon Elastic Kubernetes Service (EKS) involves setting up, deploying, and managing the popular 2048 game application on a Kubernetes cluster running on AWS EKS. This project aims to demonstrate how to containerize a web application, deploy it on EKS, manage the cluster, and expose the application to users.

1. Containerization:

I began by containerizing the 2048 game using Docker. This involved creating a Dockerfile to define the application's runtime environment and dependencies, ultimately resulting in a Docker image ready for deployment.

2. Deployment:

The containerized 2048 game was deployed on the EKS cluster using Kubernetes. I defined Kubernetes deployment and service YAML files to ensure the application's efficient management and availability.

3. Scaling and Management:

I explored Kubernetes's scaling capabilities, adjusting the number of application replicas based on demand. This ensured the game could handle varying levels of user traffic seamlessly

4. Application Exposure:

To make the 2048 game accessible to users, I created a Kubernetes service to expose it securely over the internet. Additionally, I could have implemented an Ingress controller for more advanced routing

# Create an EKS cluster 

Deploy the EKS cluster using terraform eks.tf

terraform init - to initialize the terraform directory
![alt text](image.png)

terraform plan - To see what will be deployed
![alt text](image-1.png)

terraform apply - This will the infrastructure provision


