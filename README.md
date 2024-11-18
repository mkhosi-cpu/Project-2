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

terraform apply - This will begin the infrastructure provision with all specified resorces

# Resources deployed using terrafom

#IAM Role for EKS Cluster

#Attach AmazonEKSClusterPolicy to Cluster Role

#IAM Role for EKS Node Group

#Attach Policies to Node Group Role

#Fetch Default VPC

#Fetch Subnets across multiple AZs

#Security Group for EKS Cluster

#EKS Cluster

#EKS Node Group

#EKS Addons

# Create a new POD in EKS for the 2048 game

 kubectl apply -f 2048-pod.yaml - apply the config file to create the pod

#pod/2048-pod created

 kubectl get pods - view the newly created pod
 ![alt text](image-3.png)

 # Setup Load Balancer Service

kubectl apply -f 2048-svc.yaml - apply the config file 

kubectl describe svc game-2048-svc - view details of the modified service 
![alt text](image-4.png)

Access the LoadBalancer Ingress on the kops instance curl <LoadBalancer_Ingress>:<Port_number> or curl acdca27d38e8b456d8bb23081404284b-1473205293.us-east-1.elb.amazonaws.com:80 

To access the game : acdca27d38e8b456d8bb23081404284b-1473205293.us-east-1.elb.amazonaws.com:80 
![alt text](image-5.png)








