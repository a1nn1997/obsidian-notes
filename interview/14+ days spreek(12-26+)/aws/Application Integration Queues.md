
```json
"Application Integration": [

        "SQS",

        "SNS",

        "MQ"

    ]
```

```json
[

    {

        "service_name": "SQS",

        "service_type": "Application Integration",

        "description": "Amazon Simple Queue Service (SQS) is a managed message queue service that enables decoupling of microservices, distributed systems, and serverless apps.",

        "usage": "Message processing, worker queues, decoupling architectures.",

        "extra_info": {

            "Standard Queues": "Nearly unlimited throughput, at-least-once delivery.",

            "FIFO Queues": "Guaranteed once-only message processing.",

            "Visibility Timeout": "Time a message is hidden after being read.",

            "Dead Letter Queue": "Handle failed message processing.",

            "Message Retention": "Time messages are kept if not deleted.",

            "Delay Queues": "Delay delivery of new messages.",

            "Polling": "Retrieve messages from the queue.",

            "Batch Operations": "Send and delete multiple messages.",

            "Event Source": "Trigger AWS Lambda from SQS.",

            "Encryption": "Secure messages in transit and at rest."

        }

    },

    {

        "service_name": "SNS",

        "service_type": "Application Integration",

        "description": "Amazon Simple Notification Service (SNS) is a fully managed messaging service for both application-to-application and application-to-person communication.",

        "usage": "Send alarms, notifications, or trigger workflows.",

        "extra_info": {

            "Topics": "Access points for recipients to dynamically subscribe.",

            "Publishers": "Entities producing messages to topics.",

            "Subscribers": "Entities receiving messages from topics.",

            "Protocols": "Supports SMS, Email, SQS, Lambda, HTTPS, etc.",

            "Filter Policies": "Filter messages before sending to subscribers.",

            "Message Attributes": "Metadata to structure message data.",

            "FIFO Topics": "Guaranteed once-only message delivery and ordering.",

            "Message Archiving": "Store messages for compliance.",

            "Encryption": "Secure messages in transit and at rest.",

            "Application Integration": "Trigger AWS services from messages."

        }

    },

    {

        "service_name": "MQ",

        "service_type": "Application Integration",

        "description": "Amazon MQ is a managed message broker service for ActiveMQ and RabbitMQ.",

        "usage": "Messaging service for app decoupling and integration.",

        "extra_info": {

            "Fully Managed": "Automated provisioning, operation, and scaling.",

            "Supports Popular Brokers": "Supports ActiveMQ and RabbitMQ.",

            "Persistent Messaging": "Message durability and delivery assurance.",

            "Migration Support": "Migrate on-premises brokers to AWS.",

            "Multi-Availability Zone": "High availability with failover.",

            "Security": "Encryption at rest and in transit.",

            "Network Isolation": "Deploy within VPC for isolation.",

            "Monitoring": "Integrated with CloudWatch.",

            "Logging": "Integrated with CloudTrail.",

            "Scaling": "Easily scale message throughput."

        }

    }

]
```