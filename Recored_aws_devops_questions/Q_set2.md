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

## Terraform state file and terraform how to create particular resource?
In Terraform, the state file is a critical component that keeps track of the resources created and managed by Terraform for a particular infrastructure. The state file is used to map real-world resources to your configuration, enabling Terraform to know what resources exist and their current state.

When creating a particular resource in Terraform, you typically follow these steps:

1. **Write Terraform Configuration:**
   - Create a Terraform configuration file (e.g., `main.tf`) where you define the resources you want to create. For example, if you want to create an AWS S3 bucket, your configuration might look like this:

    ```hcl
    provider "aws" {
      region = "us-west-2"
    }

    resource "aws_s3_bucket" "my_bucket" {
      bucket = "my-unique-bucket-name"
      acl    = "private"
    }
    ```

   - In this example, an S3 bucket named "my-unique-bucket-name" with private access control is defined.

2. **Initialize Terraform:**
   - Run the following command in your terminal to initialize the Terraform working directory:

    ```bash
    terraform init
    ```

   - This command downloads the necessary providers and initializes the working directory with Terraform configurations.

3. **Plan the Changes:**
   - Run the following command to see what changes Terraform will make to create the specified resources:

    ```bash
    terraform plan
    ```

   - This step allows you to review the planned changes before applying them.

4. **Apply the Changes:**
   - Once you are satisfied with the plan, apply the changes by running:

    ```bash
    terraform apply
    ```

   - Terraform will prompt you to confirm that you want to apply the changes. Type "yes" and press Enter.

5. **Inspect the State File:**
   - Terraform will create a state file (by default named `terraform.tfstate`) that contains information about the resources created. You can inspect this file to see the current state of your infrastructure.

## Disadvantage of ami in aws?
1. **Limited Portability:**
   - AMIs are specific to the AWS environment, making them less portable compared to containerized solutions. If you decide to migrate your application to a different cloud provider or on-premises environment, you may need to reconfigure and recreate your images.

2. **Size and Storage Costs:**
   - AMIs can be large in size, especially for instances with significant data and applications pre-installed. Storing and managing large AMIs can result in higher storage costs. Additionally, transferring large AMIs between AWS regions incurs data transfer costs.

3. **Maintenance Overhead:**
   - Keeping AMIs up-to-date with the latest patches, updates, and security fixes can be a manual and time-consuming process. Regular maintenance is essential to ensure that instances launched from AMIs have the latest security updates.

4. **Potential Security Risks:**
   - If an AMI is not properly maintained and regularly updated, it can pose security risks. Outdated software and configurations may contain vulnerabilities that could be exploited.

5. **Limited Customization at Launch Time:**
   - While AMIs provide a snapshot of an instance, customization options at launch time may be limited. Some configurations, such as instance type or security group settings, may need to be adjusted separately.

## What is kublet?
In Kubernetes (K8s), the kubelet is a critical component responsible for communication between the Kubernetes master node and the individual nodes (or minions) in the cluster. Running on each node, the kubelet manages the containers and ensures that they are running in a healthy state as defined by the pod specifications received from the control plane. It interacts with container runtimes, such as Docker or containerd, to start, stop, and monitor containers, while also reporting back to the master node about the node's overall health and resource availability.

## what is Container runtime in k8s?
In Kubernetes (K8s), a container runtime is the software responsible for executing and managing containers within a cluster. It abstracts the low-level details of interacting with the underlying operating system and facilitates the deployment and execution of containerized applications. Popular container runtimes compatible with Kubernetes include Docker, containerd, and others. The container runtime interfaces with the K8s kubelet on each node to start, stop, and manage containers based on the specifications defined in Kubernetes pods.

## S3 object lock and how to give permission to particular user to bucket?
Amazon S3 Object Lock is a feature that allows you to apply retention settings to your objects to prevent them from being deleted or overwritten for a specified retention period. This helps you meet compliance requirements and data governance needs.

To set up S3 Object Lock and give permissions to a particular user for a bucket, you'll need to perform the following steps:

### 1. Enable S3 Object Lock on the Bucket:
   - Log in to the AWS Management Console.
   - Navigate to the S3 service.
   - Select the bucket for which you want to enable Object Lock.
   - Click on the "Management" tab.
   - Choose "Object lock" from the left-hand menu.
   - Click on "Edit retention" to configure retention settings for the bucket.

### 2. Configure Object Lock Settings:
   - Choose one of the retention modes: Governance or Compliance.
   - Specify a retention period for the objects in the bucket.

### 3. Define Object Lock Permissions:

#### a. IAM User Policy:
   - Go to the IAM (Identity and Access Management) service in the AWS Management Console.
   - Create a new IAM policy that grants the necessary permissions for S3 Object Lock. Below is a sample policy:
     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Effect": "Allow",
           "Action": [
             "s3:GetObjectRetention",
             "s3:GetObjectLegalHold",
             "s3:PutObjectRetention",
             "s3:PutObjectLegalHold"
           ],
           "Resource": "arn:aws:s3:::your-bucket-name/*"
         }
       ]
     }
     ```
   - Replace "your-bucket-name" with the actual name of your S3 bucket.

#### b. Attach Policy to IAM User:
   - Attach the newly created policy to the IAM user who needs permission to manage Object Lock settings on the bucket.

### 4. Verify Permissions:
   - Test the setup by having the IAM user perform actions related to Object Lock on S3 objects in the specified bucket.

## How to create slaves in jenkins?
Creating nodes in Jenkins is a common task to distribute build and deployment workloads across multiple machines. These nodes, also known as agents, can be set up on different physical or virtual machines to parallelize tasks and improve overall efficiency. Here are the general steps to create nodes in Jenkins:

1. **Access Jenkins Dashboard:**
   - Open your web browser and navigate to your Jenkins instance (http://your-jenkins-server:8080).

2. **Login to Jenkins:**
   - Log in using your credentials if required.

3. **Navigate to Manage Jenkins:**
   - Click on "Manage Jenkins" on the Jenkins dashboard.

4. **Configure Global Security (if necessary):**
   - If you have security enabled, go to "Configure Global Security" and ensure that "TCP port for JNLP agents" is not disabled.

5. **Manage Nodes:**
   - In the "Manage Jenkins" page, click on "Manage Nodes and Clouds."

6. **Add a New Node:**
   - Click on the "New Node" or "New Agent" button, depending on your Jenkins version.

7. **Configure Node Details:**
   - Provide a name for your node.
   - Choose the type of node. For most cases, you'll use "Permanent Agent."
   - Click "OK" or "Save" to proceed to the configuration page for the new node.

8. **Configure Node Settings:**
   - Fill in the required information for the node, including labels, the number of executors (parallel jobs it can handle), and the root directory.

9. **Launch Method:**
   - Choose the launch method for the agent. Common options include:
     - Launch agent via execution of command on the master.
     - Launch agent agents via Java Web Start.

10. **Save Node Configuration:**
    - Save your changes and go back to the "Nodes and Clouds" page.

11. **Connect the Node:**
    - On the "Nodes and Clouds" page, find your newly created node and click on it.
    - Follow the instructions to connect the node to Jenkins. This might involve copying a command to run on the agent machine or downloading a JNLP file.

12. **Verify Connection:**
    - Once the node is connected, Jenkins should recognize it as an available agent.

## High level about DR?
Disaster recovery (DR) is a strategic approach that organizations implement to ensure business continuity in the face of unforeseen disruptions, such as natural disasters, cyber attacks, or hardware failures. It involves creating comprehensive plans, processes, and infrastructure to swiftly recover and restore critical IT systems, data, and operations to minimize downtime and ensure minimal impact on business functions. DR strategies typically include regular backups, offsite data storage, redundancy, and the ability to quickly switch to alternative systems or locations, enabling organizations to resume normal operations efficiently and safeguard against potential data loss or extended service interruptions.

## Who to create HA in jenkins?
Creating High Availability (HA) in Jenkins involves setting up a resilient and fault-tolerant infrastructure to ensure continuous availability of Jenkins services. Here's a high-level guide on how to achieve High Availability in Jenkins:

1. **Load Balancing:**
   - Deploy a load balancer to distribute incoming traffic across multiple Jenkins instances. This ensures that the workload is evenly distributed and provides a single entry point for users.

2. **Database Replication:**
   - Implement database replication to create a redundant database system. This involves setting up a master-slave configuration for the Jenkins database, where changes made to the master database are replicated to one or more slave databases.

3. **Shared File System:**
   - Configure a shared file system to store Jenkins configurations, plugins, and job data. This ensures consistency across all Jenkins instances in the HA setup.

4. **Session Persistence:**
   - Enable session persistence to maintain user sessions even if they switch between different Jenkins instances. This is crucial for providing a seamless experience as users interact with the HA Jenkins environment.

5. **Artifact Repository:**
   - Set up a centralized artifact repository to store build artifacts. This ensures that all Jenkins instances in the HA setup have access to the same artifacts, promoting consistency in builds.

6. **Distributed Build Executors:**
   - Implement a distributed build architecture where build executors are spread across multiple Jenkins nodes or agents. This helps distribute build workloads and ensures that builds can continue even if one node goes down.

7. **Monitoring and Alerts:**
   - Implement monitoring tools to keep track of the health and performance of the Jenkins infrastructure. Set up alerts to notify administrators of any issues so they can take proactive measures.

8. **Automated Backups:**
   - Regularly backup Jenkins configurations, job definitions, and critical data. Having automated backup processes in place is essential for quick recovery in case of failures.

9. **Redundancy for Critical Components:**
   - Identify critical components in the Jenkins infrastructure, such as the load balancer, database, and shared file system, and ensure redundancy for these components. This may involve setting up backup instances or failover mechanisms.

10. **Documentation and Testing:**
    - Document the HA configuration thoroughly, including procedures for maintenance and recovery. Regularly test the HA setup to validate its effectiveness and identify any potential issues.

## How to start and stop the pod?
In Kubernetes (K8s), you manage applications by defining resources, and one of these resources is a "Pod." A Pod represents a running process in a cluster and can contain one or more containers. To start and stop a Pod in Kubernetes, you typically create and delete the Pod using YAML configuration files or imperative commands. Here's a basic guide:

### Starting a Pod:

1. **Using YAML Configuration:**
   - Create a YAML file describing your Pod. Save it, for example, as `pod.yaml`.

     ```yaml
     apiVersion: v1
     kind: Pod
     metadata:
       name: mypod
     spec:
       containers:
       - name: mycontainer
         image: nginx:latest
     ```

   - Apply the configuration using the `kubectl apply` command:

     ```bash
     kubectl apply -f pod.yaml
     ```

   This will create the Pod based on the configuration in the YAML file.

2. **Imperative Command:**
   - Alternatively, you can create a Pod imperatively using the `kubectl run` command:

     ```bash
     kubectl run mypod --image=nginx:latest
     ```

   This command creates a Pod named `mypod` with the specified Docker image (`nginx:latest` in this example).

### Stopping (Deleting) a Pod:

1. **Using YAML Configuration:**
   - To delete a Pod, you can use the `kubectl delete` command and specify the YAML file:

     ```bash
     kubectl delete -f pod.yaml
     ```

2. **Imperative Command:**
   - To delete a Pod imperatively, use the `kubectl delete pod` command and specify the Pod's name:

     ```bash
     kubectl delete pod mypod
     ```

### Checking Pod Status:

- You can check the status of your Pod using the `kubectl get pods` command:

  ```bash
  kubectl get pods
  ```

  This will display the current status of all Pods in the namespace.

## Kuberntes cost optimisation?
Optimizing costs in a Kubernetes environment involves efficiently utilizing resources, managing infrastructure wisely, and adopting best practices to minimize expenses. Here are several strategies for Kubernetes cost optimization:

1. **Right-size Resources:**
   - Ensure that you allocate the right amount of resources (CPU and memory) to your containers. Overprovisioning can lead to unnecessary costs. Regularly monitor resource usage and adjust as needed.

2. **Horizontal Pod Autoscaling (HPA):**
   - Implement Horizontal Pod Autoscaling to automatically adjust the number of running Pods based on resource utilization. This helps scale your applications dynamically in response to varying workloads.

3. **Cluster Autoscaler:**
   - Use the Cluster Autoscaler to automatically adjust the size of your Kubernetes cluster based on demand. This ensures that you have enough nodes to handle your workloads efficiently.

4. **Optimize Storage:**
   - Choose appropriate storage classes for your persistent volumes based on your application's requirements. Avoid unnecessary use of high-performance storage for non-critical workloads.

5. **Pod Disruption Budgets:**
   - Implement Pod Disruption Budgets to control the number of simultaneous disruptions allowed during voluntary disruptions, such as rolling updates. This helps maintain availability while minimizing resource costs.

6. **Spot Instances (AWS), Preemptible VMs (GCP), and Spot Nodes (Azure):**
   - Take advantage of spot instances, preemptible VMs, or spot nodes offered by cloud providers for non-critical workloads. These instances are usually significantly cheaper but can be terminated with short notice.

7. **Reserved Instances (AWS), Committed Use Discounts (GCP), Reserved VM Instances (Azure):**
   - For predictable workloads, consider using reserved instances or committed use discounts to commit to a specific amount of resources over a fixed period, offering cost savings compared to on-demand pricing.

8. **Resource Quotas and Limits:**
   - Set resource quotas to limit the amount of resources consumed by namespaces and enforce resource limits at the Pod level. This prevents individual Pods from consuming excessive resources and helps avoid unexpected costs.

9. **Idle Resources Cleanup:**
   - Regularly review and clean up idle resources, including unused Pods, Deployments, or services. This ensures that you are only paying for resources that actively contribute to your applications.

10. **Cost Monitoring and Reporting:**
    - Use tools and services for cost monitoring and reporting. Cloud providers often offer dashboards and tools that provide insights into resource usage and costs. Third-party tools can also help in analyzing and optimizing expenses.

11. **Efficient Image Management:**
    - Optimize Docker images to reduce their size, leading to faster deployments and reduced storage costs. Avoid unnecessary packages and layers in your container images.

12. **Logging and Monitoring Optimization:**
    - Fine-tune logging and monitoring configurations to avoid unnecessary data transfer and storage costs. Set up efficient log retention policies and use sampling for monitoring data when appropriate.

