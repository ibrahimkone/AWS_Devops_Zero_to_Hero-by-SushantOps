## How to increase node in eks?
To increase the number of nodes in an Amazon EKS (Elastic Kubernetes Service) cluster, you can modify the node group associated with your cluster. This involves adjusting the desired capacity of the node group to add more EC2 instances. First, identify the node group you want to scale, then update its configuration using the AWS Management Console, AWS CLI, or an infrastructure-as-code tool like Terraform. Specify the new desired capacity to reflect the additional nodes you want. EKS will automatically adjust the cluster size, deploying new nodes to meet the desired capacity. Keep in mind factors like instance type, AMI, and networking requirements when scaling to ensure compatibility with your application workloads.

## what is Sticky session?
Sticky sessions, also known as session affinity, refer to a mechanism in web server load balancing where a user's requests are consistently directed to the same server throughout their session. This is achieved by associating a user's initial connection with a specific server and then ensuring that subsequent requests from the same user are directed to that server. Sticky sessions are useful for applications that store session data on the server side, ensuring a seamless user experience by maintaining continuity in accessing session-related information, such as login credentials or shopping cart contents.

## what is Jenkins shared library

## Connection draining in load balancer

## Routing polices in route53

## What encryption method u used for s3 bucket

## Auto scaling polices

## Work load in kubernates

## Terraform state file and terraform how to create particular resource

## Disadvantage of ami

## What is kublet

## Container runtime

## S3 object lock and how to give permission to particular user to bucket

## How can u create read replica in rds

## How you scale read replica

## What is weightied police in route 53

## How to create slaves in jenkins

## High level about DR

## Who to create HA in jenkins

## How to start and stop the pod

## Cost optimisation

## Kuberntes cost optimisation
