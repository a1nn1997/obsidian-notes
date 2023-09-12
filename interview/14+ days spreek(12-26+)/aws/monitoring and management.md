```json

    "Monitoring & Management": [

        "CloudWatch",

        "CloudTrail",

        "CloudFormation"

    ],
```


```json
[

    {

        "service_name": "CloudWatch",

        "service_type": "Monitoring & Management",

        "description": "Amazon CloudWatch provides monitoring and observability of AWS resources and applications.",

        "usage": "Monitoring AWS resources, setting alarms, collecting performance data.",

        "extra_info": {

            "Metrics": "Time-ordered data for resources and applications.",

            "Alarms": "Notify when thresholds are breached.",

            "Events": "Stream system events depicting changes.",

            "Logs": "Aggregate and store logs from resources.",

            "Dashboards": "Visualize metrics, logs, and alarms.",

            "Anomaly Detection": "Uses ML to detect anomalies in metrics.",

            "ServiceLens": "Visualize and analyze performance and availability.",

            "Log Insights": "Interactive log analytics and visualization.",

            "Embedded Metric Format": "Send custom metrics with log events.",

            "Resource Health": "Gain insight into resource health and incidents."

        }

    },

    {

        "service_name": "CloudTrail",

        "service_type": "Management & Governance",

        "description": "AWS CloudTrail tracks user activity and API usage, providing visibility into user and resource activity.",

        "usage": "Audit, compliance, operational troubleshooting, and security incident investigation.",

        "extra_info": {

            "Event History": "View recent account activity.",

            "Trail": "Record ongoing events in logs.",

            "Digest Files": "List of log files written and hash values for validation.",

            "Log File Integrity": "Verify the integrity of delivered log files.",

            "Log File Encryption": "Encrypt using KMS keys.",

            "S3 Data Events": "Record API calls for S3 object-level operations.",

            "Lambda Data Events": "Record Lambda function execution activity.",

            "Lookup Events": "Retrieve specific events.",

            "Insights": "Identify unusual activity.",

            "Multi-Region": "Record events in all global regions."

        }

    },

    {

        "service_name": "CloudFormation",

        "service_type": "Management & Governance",

        "description": "AWS CloudFormation provides a common language to describe and provision resources in AWS.",

        "usage": "Infrastructure as Code (IaC) for consistent AWS resource deployment.",

        "extra_info": {

            "Templates": "Define resource configurations in YAML or JSON.",

            "Stacks": "Provision related resources as a unit.",

            "Rollbacks": "Automatic rollback on error.",

            "Change Sets": "Preview changes before applying.",

            "Designer": "Visual tool for creating templates.",

            "Drift Detection": "Identify resources that differ from the stack's template.",

            "Resource Import": "Bring existing AWS resources into CloudFormation management.",

            "Nested Stacks": "Reuse common template patterns.",

            "Safe Deployments": "Use with CodeDeploy for blue/green deployments.",

            "Extensibility": "Custom resources and macros."

        }

    }

]
```