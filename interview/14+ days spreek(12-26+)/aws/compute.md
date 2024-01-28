```json

    "Compute": [

        "EC2",

        "Lambda",

        "ECS",

        "EKS",

        "Elastic Beanstalk",

        "Fargate"

    ],
```

```json
[

    {

        "service_name": "EC2",

        "service_type": "Compute",

        "description": "Amazon Elastic Compute Cloud (EC2) is a web service offering scalable compute capacity in the cloud.",

        "usage": "Host web servers, applications, databases, and more.",

        "extra_info": {

            "Instances": "Virtual servers hosted in EC2.",

            "AMI": "Amazon Machine Images define initial software on an instance.",

            "EBS": "Elastic Block Store provides persistent storage for instances.",

            "Instance Types": "Different configurations of CPU, memory, storage for instances.",

            "Security Groups": "Firewall rules defining traffic to and from instances.",

            "Elastic IP": "Static IPv4 addresses for dynamic cloud computing.",

            "VPC": "Virtual Private Cloud to logically isolate resources.",

            "Placement Groups": "Logical grouping for instances based on specific needs.",

            "Spot Instances": "Bid-based pricing model for unused EC2 capacity.",

            "Elastic Load Balancing": "Distribute incoming traffic across multiple targets."

        }

    },

    {

        "service_name": "Lambda",

        "service_type": "Compute",

        "description": "AWS Lambda lets you run code without provisioning or managing servers. You pay only for the compute time you consume.",

        "usage": "Event-driven computing, serverless applications, data processing.",

        "extra_info": {

            "Triggers": "Lambda functions can be triggered by other AWS services or HTTP requests.",

            "Scaling": "Automatically scales up or down based on the number of events.",

            "Languages": "Supports Node.js, Python, Ruby, Java, Go, .NET Core, etc.",

            "Stateless": "Each function execution is stateless.",

            "Layers": "Reusable components across functions.",

            "Monitoring": "Integrated with CloudWatch for monitoring.",

            "Concurrency": "Multiple invocations run in parallel.",

            "Built-in Fault Tolerance": "Maintains compute capacity and infrastructure reliability.",

            "VPC Access": "Can access resources in a VPC.",

            "Versioning": "Publish multiple versions of your Lambda function."

        }

    },

    {

        "service_name": "ECS",

        "service_type": "Compute",

        "description": "Amazon Elastic Container Service (ECS) is a container management service that supports Docker containers.",

        "usage": "Run containerized applications, microservices.",

        "extra_info": {

            "Tasks": "Definitions for Docker containers to run together.",

            "Services": "Maintain a specified number of task instances.",

            "Clusters": "Logical grouping of resources for tasks and services.",

            "Fargate": "Serverless compute engine for containers.",

            "ECS Agent": "Software on EC2 instances to connect them to the cluster.",

            "Service Discovery": "Use Route 53 to discover services in a cluster.",

            "Logging": "Integrate with CloudWatch for logs.",

            "Task Networking": "Assign elastic network interfaces to tasks.",

            "Elastic Load Balancing": "Distribute traffic across services.",

            "Resource Limits": "Specify and manage compute limits."

        }

    },

  
{

        "service_name": "EKS",

        "service_type": "Compute",

        "description": "Amazon Elastic Kubernetes Service (EKS) is a managed Kubernetes service.",

        "usage": "Run Kubernetes applications, manage containerized workloads.",

        "extra_info": {

            "Clusters": "Hosts Kubernetes control plane instances.",

            "Worker Nodes": "EC2 instances running containers.",

            "Fargate": "Run Kubernetes pods using serverless infrastructure.",

            "Networking": "Integrate with AWS VPC for isolated networking.",

            "EKS Console": "Visualize and manage clusters and workloads.",

            "Logging": "Integrate with CloudWatch and CloudTrail.",

            "IAM Integration": "Assign roles to Kubernetes service accounts.",

            "Load Balancing": "Use ELB to distribute traffic.",

            "Persistent Storage": "Integrate with EBS for data.",

            "Security Groups": "Use with worker nodes for enhanced security."

        }

    },

    {

        "service_name": "Elastic Beanstalk",

        "service_type": "Compute",

        "description": "AWS Elastic Beanstalk is a fully managed service for deploying, managing, and scaling web applicationcs and services.",

        "usage": "App deployment, management, and scaling without infrastructure management.",

        "extra_info": {

            "Platform Support": "Supports Java, .NET, PHP, Node.js, Python, Ruby, Go, Docker.",

            "Scaling": "Automatic scaling based on traffic patterns.",

            "Environment Monitoring": "Dashboard for application health and resource usage.",

            "Integrated Developer Tools": "CLI and IDE integration.",

            "Deployment Options": "In-place or Blue/Green deployments.",

            "Extension": "Use configuration files to customize environment.",

            "Health Checks": "Monitor application health.",

            "Version Management": "Keep and switch between app versions.",

            "Logs": "Integrated with CloudWatch for logs.",

            "Updates": "Managed platform updates."

        }

    },

    {

        "service_name": "Fargate",

        "service_type": "Compute",

        "description": "AWS Fargate is a serverless compute engine for containers, eliminating the need to manage the underlying EC2 instances.",

        "usage": "Run containers without managing servers or clusters.",

        "extra_info": {

            "Serverless": "Automatically scales, manages, and operates container infrastructure.",

            "Cost-Optimized": "Pay only for the vCPU and memory resources used.",

            "Integrated": "Works with ECS and EKS for orchestration.",

            "Security": "Isolation by design through VM-level isolation.",

            "Task Networking": "Assign elastic network interface to tasks.",

            "Ephemeral Storage": "Temporary storage for tasks.",

            "Resource-Level Permissions": "Fine-grained control via IAM.",

            "CloudWatch Integration": "Monitor and log container health and metrics.",

            "Application Load Balancing": "Distribute traffic across containers.",

            "VPC Support": "Launch containers in a VPC."

        }

    }

]
```

