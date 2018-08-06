## Retention

* Data points with a period of less than 60 seconds are available for 3 hours. These data points are high-resolution custom metrics.
* Data points with a period of 60 seconds (1 minute) are available for 15 days
* Data points with a period of 300 seconds (5 minute) are available for 63 days 
* Data points with a period of 3600 seconds (1 hour) are available for 455 days (15 months)

Amazon CloudWatch stores metrics for terminated Amazon EC2 instances or deleted Elastic Load Balancers for 15 months.

You can store your log data in CloudWatch Logs for as long as you want. By default, CloudWatch Logs will store your log data indefinitely. You can change the retention for each Log Group at any time.

Alarm history is available for 14 days.

You can retrieve, graph, and set alarms on the following statistical values for Amazon CloudWatch metrics: Average, Sum, Minimum, Maximum, and Sample Count. Statistics can be computed for any time periods between 60-seconds and 1-day. For high-resolution custom metrics, statistics can be computed for time periods between 1-second and 3-hours.

## Metrics

Be familiar with some common metrics used for monitoring.There are many metrics available, and not all of them are tested on the exam. Some are tested, however, and it is a good idea to know the common ones: VolumeQueueLength, DatabaseConnections, DiskQueueDepth, FreeStorageSpace, ReplicaLag, ReadIOPS, WriteIOS, ReadLatency, WriteLatency, SurgeQueueLength, and SpilloverCount.  DESCRIBE THESE


## Custom Metrics and Events

* A custom metric can be one of the following:
* Standard resolution, with data having one-minute granularity
* High resolution, with data at a granularity of one second

Your applications can emit custom events by using the PutEvents API.

Amazon CloudWatch has standard metrics for many views of which the underlying system is aware, such as CPU utilization and Amazon EBS disk latency. AWS does not access the internals of a customer’s instance, however. Therefore, you would need to create a custom metric and push the measurements from inside the instance to Amazon CloudWatch service for items like RAM utilization.

CloudWatch Events is able to generate events on a schedule you set by using the popular Unix cron syntax.

When an event matches a rule you've created in the system, you can automatically invoke an AWS Lambda function, relay the event to an Amazon Kinesis stream, notify an Amazon SNS topic, or invoke a built-in workflow.

Currently, Amazon EC2, Auto Scaling, and AWS CloudTrail are supported. Via AWS CloudTrail, mutating API calls (i.e., all calls except Describe*, List*, and Get*) across all services are visible in CloudWatch Events.

Amazon CloudWatch Events has three components: Events, Rules, and Targets.Events indicate a change in an AWS environment. Targets process events. Rules match incoming events and route them to targets for processing.

Visibility for metrics above the Hypervisor requires an agent.Amazon CloudWatch can tell you CPU and RAM utilization at the Hypervisor level but it has no way of knowing what specific tasks or processes are affecting performance. CloudWatch can see disk I/ O but cannot see disk usage. To do this requires an agent.


## Frequency and Resolution

When you publish a high-resolution metric, CloudWatch stores it with a resolution of 1 second, and you can read and retrieve it with a period of 1 second, 5 seconds, 10 seconds, 30 seconds, or any multiple of 60 seconds.

The CloudWatch Logs Agent will send log data every five seconds by default and is configurable by the user.

Amazon Relational Database Service sends metrics to CloudWatch for each active database instance every minute. Detailed monitoring is enabled by default.

Amazon CloudWatch monitors the number of healthy hosts, average latency, number of requests, and several other metrics in 60-second intervals as a standard metric for load balancers.

## Alarms

Alarms can perform actions.  The action can be an Amazon EC2 action, an Auto Scaling action, or a notification sent to an Amazon SNS topic.

The action can be an Amazon EC2 action, an Auto Scaling action, or a notification sent to an Amazon SNS topic.

Degraded and Severely Degraded performance means that the EBS Volume Status Check is in a Warning state and there is some I/ O. Stalled or Not Available means that the EBS Volume is in the Impaired state, and there is no I/ O.


## Variations

By default, basic monitoring is enabled when you create a launch configuration using the AWS Management Console, and detailed monitoring is enabled when you create a launch configuration using the AWS CLI or an API.

Amazon Route 53 sends metrics to CloudWatch. CloudWatch provides detailed monitoring of Amazon Route 53 by default. Amazon Route 53 sends one-minute metrics to CloudWatch.


## Logs, Filters, Dashboards

CloudWatch Logs can ingest, aggregate and monitor any text based common log data or JSON-formatted logs.

Amazon CloudWatch Metric Filters does not support regular expressions. To process your log data with regular expressions, consider using Amazon Kinesis

A dashboard is available to anyone with the correct permissions for the account with the dashboard.


## Specific Metrics

FreeStorageSpace monitors the amount of available storage space for a DB instance and it is measured in bytes.

When the SurgeQueueLength is exceeded, spillover occurs. Requests are dropped without notifying end users. Customer experience is negatively impacted.


## put-metrics

put-metric-data publishes metric data points to Amazon CloudWatch. Amazon CloudWatch associates the data points with the specified metric. If the specified metric does not exist, Amazon CloudWatch creates the metric. When Amazon CloudWatch creates a metric, it can take up to 15 minutes for the metric to appear. 

Your applications can emit custom events by using the PutEvents API.


## Monitoring Plan

Know how to create a monitoring plan.Creating a monitoring plan involves answering some basic questions. What are your goals for monitoring? What resources will you monitor? How often will you monitor these resources? What monitoring tools will you use? Who will perform the monitoring tasks? Who should be notified when something goes wrong?
