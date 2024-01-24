## How to increase node in eks?
To increase the number of nodes in an Amazon EKS (Elastic Kubernetes Service) cluster, you can modify the node group associated with your cluster. This involves adjusting the desired capacity of the node group to add more EC2 instances. First, identify the node group you want to scale, then update its configuration using the AWS Management Console, AWS CLI, or an infrastructure-as-code tool like Terraform. Specify the new desired capacity to reflect the additional nodes you want. EKS will automatically adjust the cluster size, deploying new nodes to meet the desired capacity. Keep in mind factors like instance type, AMI, and networking requirements when scaling to ensure compatibility with your application workloads.

## what is Sticky session?
Sticky sessions, also known as session affinity, refer to a mechanism in web server load balancing where a user's requests are consistently directed to the same server throughout their session. This is achieved by associating a user's initial connection with a specific server and then ensuring that subsequent requests from the same user are directed to that server. Sticky sessions are useful for applications that store session data on the server side, ensuring a seamless user experience by maintaining continuity in accessing session-related information, such as login credentials or shopping cart contents.

## what is Jenkins shared library?
Jenkins shared library is a reusable and centralized set of Groovy code and resources that can be shared across multiple Jenkins pipelines. It allows organizations to define and manage common functions, methods, and workflows in a single codebase, promoting consistency and reusability in their Continuous Integration/Continuous Deployment (CI/CD) processes. Shared libraries simplify pipeline maintenance, encourage best practices, and facilitate collaboration among development teams by providing a standardized way to manage and version control shared code logic in Jenkins pipelines.

## Connection draining in load balancer?
Connection draining in a load balancer is like allowing a graceful exit for a server that needs to be taken out of service. Imagine a busy restaurant where the chef is about to take a break. Instead of immediately turning away hungry customers, the restaurant manager allows the chef to finish cooking for current orders before closing the kitchen. Similarly, connection draining ensures that the load balancer doesn't abruptly stop sending new requests to a server that's being removed. Instead, it lets existing connections complete their tasks before fully redirecting new requests to other servers, preventing disruptions and ensuring a smoother transition during maintenance or scaling activities.

## Routing polices in route53?
1. **Simple Routing:** Directs traffic to a single resource, such as an Amazon S3 bucket or an Elastic Load Balancer (ELB).

2. **Weighted Routing:** Distributes traffic among multiple resources based on assigned weights. You can specify the percentage of traffic each resource receives.

3. **Latency-Based Routing:** Routes traffic to the resource with the lowest latency from the end user's location. This is particularly useful for applications hosted in multiple AWS regions.

4. **Failover Routing:** Diverts traffic to a backup resource if the primary one becomes unhealthy. It's commonly used for setting up active-passive architectures.

5. **Geolocation Routing:** Directs traffic based on the geographic location of the end user. This allows you to customize content or direct users to specific servers based on their location.

6. **Multivalue Answer Routing:** Returns multiple IP addresses for a domain, and Route 53 randomly chooses one. Useful for distributing traffic across multiple resources.

## What encryption method u used for s3 bucket?
Amazon S3 provides several options for encrypting data at rest:

1. **Server-Side Encryption (SSE):**
   - **SSE-S3:** Amazon S3 manages keys and performs encryption and decryption on your behalf.
   - **SSE-KMS (Key Management Service):** You use AWS Key Management Service to manage keys used for encryption.

2. **Client-Side Encryption:**
   - You manage encryption and decryption processes on the client side, and S3 stores the encrypted data. The client application is responsible for managing encryption keys.

3. **Bucket Policy and ACLs:**
   - You can use S3 bucket policies and access control lists (ACLs) to control access to your buckets and objects.

## Auto scaling polices?
There are two main types of Auto Scaling policies:

1. **Scale-Out Policy:**
   - **Definition:** This policy defines the conditions under which new instances are added to the Auto Scaling group to handle increased load.
   - **Metrics:** You set specific metrics (e.g., CPU utilization, network traffic) that trigger the scaling out action.
   - **Action:** When a metric breaches a predefined threshold, Auto Scaling launches new instances to distribute the load.

2. **Scale-In Policy:**
   - **Definition:** This policy defines the conditions under which instances are removed from the Auto Scaling group to optimize resource usage during low demand.
   - **Metrics:** Similar to scale-out policies, you set metrics that indicate when it's appropriate to scale in.
   - **Action:** When a metric falls below a specified threshold, Auto Scaling terminates instances to reduce capacity.

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
