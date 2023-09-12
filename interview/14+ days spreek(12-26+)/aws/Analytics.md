
```json
"Analytics": [

        "Glue",

        "EMR",

        "Athena"

    ],
```

```json
[

    {

        "service_name": "Glue",

        "service_type": "Analytics",

        "description": "AWS Glue is a fully managed extract, transform, and load (ETL) service that makes it easy to move data among data stores.",

        "usage": "Data preparation, data loading, job scheduling.",

        "extra_info": {

            "Crawlers": "Automatically discovers and categorizes data.",

            "Data Catalog": "Centralized metadata repository.",

            "ETL Jobs": "Prepares and loads data.",

            "DataBrew": "Visual data preparation tool.",

            "Workflows": "Design and visualize ETL work.",

            "Schedulers": "Automate ETL workflows.",

            "Python & Scala": "Supported languages for job scripts.",

            "Blueprints": "Templates for creating common types of ETL jobs.",

            "Studios": "Write, debug, and run PySpark ETL code.",

            "FindMatches": "ML-based de-duplication and finding matching records."

        }

    },

    {

        "service_name": "EMR",

        "service_type": "Analytics",

        "description": "Amazon EMR provides a managed Hadoop framework that makes it easy to process vast amounts of data across resizable clusters of Amazon EC2 instances.",

        "usage": "Big data frameworks (Spark, Hive, HBase), data processing, analytics.",

        "extra_info": {

            "Resizable Clusters": "Easily scale up or down as required.",

            "Managed Frameworks": "Spark, Hive, HBase, Presto, Flink, etc.",

            "Spot Instances": "Utilize spare EC2 capacity at a discount.",

            "FSx for Lustre": "Fast, scalable storage for processing tasks.",

            "Instance Fleets": "Mix of on-demand and spot instances.",

            "EMR Notebooks": "Jupyter-based notebooks integrated with EMR.",

            "Security": "VPC, data encryption, and IAM integrations.",

            "Monitoring": "Integration with CloudWatch.",

            "EMR Studio": "IDE for developing, visualizing and debugging applications.",

            "Managed Scaling": "Automatically resizes cluster for best performance."

        }

    },

    {

        "service_name": "Athena",

        "service_type": "Analytics",

        "description": "Amazon Athena is an interactive query service that analyzes data in Amazon S3 using standard SQL.",

        "usage": "Data analysis on S3 using SQL.",

        "extra_info": {

            "Serverless": "No infrastructure management.",

            "Pay-per-query": "Charged for the queries you run.",

            "Standard SQL": "No need for complex ETL jobs.",

            "Integrated": "Works with AWS Glue Data Catalog.",

            "Result Caching": "Faster results for repeated queries.",

            "Concurrency": "Run multiple queries concurrently.",

            "Saved Queries": "Save and manage frequent SQL statements.",

            "Security": "Supports VPC, encryption and IAM.",

            "Formats": "Supports various data formats like JSON, Parquet.",

            "Visualizations": "Integrated with Amazon Quicksight for visual analytics."

        }

    }

]
```