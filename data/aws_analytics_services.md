# AWS Analytic Services

There are several AWS Analytics services and these include:

- Amazon Athena
- Amazon EMR (Elastic Map Reduce)
- Amazon CloudSearch
- Amazon Opensearch Service
- Amazon Kinesis
- Amazon QuickSight
- Amazon Data Pipeline
- AWS Glue
- AWS Lake Formation
- Amazon MSK

Focus is on Athena, EMR, Glue and Kinesis as these are the services most likely to come up on the AWS CCP exam.

# Amazon Elastic Map Reduce

Amazon EMR is a web service that enables businesses, researchers, data analysts, and developers to easily and cost-effectively process vast amounts of data.

EMR uses a hosted Hadoop framework running on Amazon EC2 and Amazon S3.

Managed Hadoop framework for processing huge amounts of data.

Also supports Apache Spark, HBase, Presto and Flink.

Most commonly used for log analysis, financial analysis, or extract, translate, loading (ETL) activities.

A Step is a programmatic task for performing some process on the data (e.g. count words).

A cluster is a collection of EC2 instances provisioned by EMR to run your steps.

EMR uses Apache Hadoop as its distributed data processing engine.
Apache Hadoop is an open source Java software framework.
Apache Hadoop supports data-intensive distributed applications running on large clusters of commodity hardware.

EMR is a good place to deploy Apache Spark.
Apache Spark is an open-sourced distributed processing for big data workloads.
Apache Spark utilizes in-memory caching and optimized query execution.

You can also launch Presto clusters.
Presto is an open-source distributed SQL query engine designed for fast analytic queries against large datasets.

EMR launches all nodes for a given cluster in the same Amazon EC2 Availability Zone.

You can access Amazon EMR by using the AWS Management Console, Command Line Tools, SDKS, or the EMR API.

With EMR, you have access to the underlying operating system (you can SSH in).

# Amazon Athena

Amazon Athena is an interactive query service tha makes it easy to analyze data in Amazon S3 using standard SQL.

Athena is serverless, so there is no infrastructure to manage, and you only pay for queries that you run.

Athena is easy to use - simply point to your data in Amazon S3, define the schema, and start querying in standard SQL.

Amazon Athena uses Presto with full standard SQL support and works with a variety of standard data formats.
Data formats include CSV, JSON, ORC, Apache Parquet, and Avro.

Amazon Athena is ideal for quick, ad-hoc querying and integrates with Amazon QuickSight for easy visualization.
However, it also handles complex analysis, including large joins, window functions, and arrays.

Amazon Athena uses a managed Data Catalog to store information and schemas about the databases and tables that you create for your data stored in Amazon S3.

# AWS Glue

AWS Glue is a fully managed, pay-as-you-go, extract, transform, and load (ETL) service.
AWS Glue automates the time-consuming steps of data preparation for analytics.

AWS Glue automatically discovers and profiles data via the Glue Data Catalog.
AWS Glue recommends and generates ETL code to transform source data into target schemas.

AWS Glue runs the ETL jobs on a fully managed, scale-out Apache Spark environment to load data into its destination.

AWS Glue allows you to set up, orchestrate, and monitor complex data flows.

You can create and run an ETL job with a few clicks in the AWS Management Console.

Use AWS Glue to discover properties of data, transform it, and prepare it for analytics.

Glue can automatically discover structured and semi-structured data stored in data lakes on Amazon S3.
Glue can also discover these in data warehouses in Amazon Redshift, and various databases running on AWS.

Glue provides a unified view of data via the Glue Data Catalog.
This data is available for ETL, querying and reporting using services like Amazon Athena, Amazon EMR, and Amazon Redshift Spectrum.

Glue automatically generates Scala or Python code for ETL jobs that you can further customize using tools you are familiar with.

AWS Glue is serverless, so there are no compute resources to configure and manage.

# Data Analysis and Query Use Cases

Query services like Amazon Athena, data warehouses like Amazon Redshift, and sophisticated data processing frameworks like Amazon EMR, all address different needs and use cases.

Amazon Redshift provides the fastest query performance for enterprise reporting and business intelligence workloads, particularly those involving extremely complex SQL with multiple joins and sub-queries.

Amazon EMR makes it simple and cost-effective to run highly distributed processing frameworks such as Hadoop, Spark, and Presto when compared to on-premises deployments. Amazon EMR is flexible – you can run custom applications and code, and define specific compute, memory, storage, and application parameters to optimize your analytic requirements.

Amazon Athena provides the easiest way to run ad-hoc queries for data in S3 without the need to set up or manage any servers.

The table below shows the primary use case and situations for using a few AWS query and analytics services:

| AWS Service     | Primary Use Case | When to Use                                                                                                                                                                                                                        |
|-----------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Amazon Athena   | Query            | Run interactive queries against data directly in Amazon S3 without worrying about formatting data or managing infrastructure. Can use with other services such as Amazon RedShift                                                  |
| Amazon RedShift | Data Warehouse   | Pull data from many sources, format and organize it, store it, and support complex, high speed queries that produce business reports.                                                                                              |
| Amazon EMR      | Data Processing  | Highly distributed processing frameworks such as Hadoop, Spark, and Presto. Run a wide variety of scale-out data processing tasks for applications such as machine learning, graph analytics, data transformation, streaming data. |
| AWS Glue        | ETL Service      | Transform and move data to various destinations. Used to prepare and load data for analytics. Data source can be S3, RedShift or another database. Glue Data Catalog can be queried by Athena, EMR and RedShift Spectrum           |

# Amazon Kinesis

Amazon Kinesis makes it easy to collect, process, and analyze real-time, streaming data so you can get timely insights and react quickly to new information.

Collection of services for processing streams of various data.

Data is processed in “shards”.

There are four types of Kinesis service, and these are detailed below.

## Kinesis Video Streams

Kinesis Video Streams makes it easy to securely stream video from connected devices to AWS for analytics, machine learning (ML), and other processing.

Durably stores, encrypts, and indexes video data streams, and allows access to data through easy-to-use APIs.

Producers provide data streams.

Stores data for 24 hours by default, up to 7 days.

Consumers receive and process data.

Can have multiple shards in a stream.

Supports encryption at rest with server-side encryption (KMS) with a customer master key.

## Kinesis Data Streams

Kinesis Data Streams enables you to build custom applications that process or analyze streaming data for specialized needs.

Kinesis Data Streams enables real-time processing of streaming big data.

Kinesis Data Streams is useful for rapidly moving data off data producers and then continuously processing the data.

Kinesis Data Streams stores data for later processing by applications (key difference with Firehose which delivers data directly to AWS services).

Common use cases include:
- Accelerated log and data feed intake.
- Real-time metrics and reporting.
- Real-time data analytics.
- Complex stream processing.

## Kinesis Data Firehose

Kinesis Data Firehose is the easiest way to load streaming data into data stores and analytics tools.

Captures, transforms, and loads streaming data.

Enables near real-time analytics with existing business intelligence tools and dashboards.

Kinesis Data Streams can be used as the source(s) to Kinesis Data Firehose.

You can configure Kinesis Data Firehose to transform your data before delivering it.

With Kinesis Data Firehose you don’t need to write an application or manage resources.

Firehose can batch, compress, and encrypt data before loading it.

Firehose synchronously replicates data across three AZs as it is transported to destinations.

Each delivery stream stores data records for up to 24 hours.

## Kinesis Data Analytics

Amazon Kinesis Data Analytics is the easiest way to process and analyze real-time, streaming data.

Can use standard SQL queries to process Kinesis data streams.

Provides real-time analysis.

Use cases:
- Generate time-series analytics.
- Feed real-time dashboards.
- Create real-time alerts and notifications.

Quickly author and run powerful SQL code against streaming sources.

Can ingest data from Kinesis Streams and Kinesis Firehose.

Output to S3, RedShift, Elasticsearch and Kinesis Data Streams.

Sits over Kinesis Data Streams and Kinesis Data Firehose.