# AWS Glue Metrics and Dimensions<a name="glue-metrics-dimensions"></a>

AWS Glue sends metrics to CloudWatch\. For more information, see [Monitoring AWS Glue Using CloudWatch Metrics](http://docs.aws.amazon.com/glue/latest/dg/monitoring-awsglue-with-cloudwatch-metrics.html) in the AWS Glue Developer Guide\.

## AWS Glue Metrics<a name="awsglue-metrics"></a>

AWS Glue profiles and sends the following metrics to CloudWatch every 30 seconds, and the AWS Glue Metrics Dashboard report them once a minute:


| Metric | Description | 
| --- | --- | 
|  `glue.driver.aggregate.bytesRead` |  The number of bytes read from all data sources by all completed Spark tasks running in all executors\.\. Valid dimensions: `JobName` \(the name of the AWS Glue Job\), `JobRunId` \(the JobRun ID\. or `ALL`\), and `Type` \(count\)\. Valid Statistics: SUM\. This metric is a delta value from the last reported value, so on the AWS Glue Metrics Dashboard, a SUM statistic is used for aggregation\.  Unit: Bytes Can be used to monitor: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html) This metric can be used the same way as the `glue.ALL.s3.filesystem.read_bytes` metric, with the difference that this metric is updated at the end of a Spark task and captures non\-S3 data sources as well\.  | 
|  `glue.driver.aggregate.elapsedTime` |  The ETL elapsed time in milliseconds \(does not include the job bootstrap times\)\. Valid dimensions: `JobName` \(the name of the AWS Glue Job\), `JobRunId` \(the JobRun ID\. or `ALL`\), and `Type` \(count\)\. Valid Statistics: SUM\. This metric is a delta value from the last reported value, so on the AWS Glue Metrics Dashboard, a SUM statistic is used for aggregation\. Unit: Milliseconds Can be used to determine how long it takes a job run to run on average\. Some ways to use the data: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html)  | 
|   `glue.driver.aggregate.numCompletedStages` |  The number of completed stages in the job\. Valid dimensions: `JobName` \(the name of the AWS Glue Job\), `JobRunId` \(the JobRun ID\. or `ALL`\), and `Type` \(count\)\. Valid Statistics: SUM\. This metric is a delta value from the last reported value, so on the AWS Glue Metrics Dashboard, a SUM statistic is used for aggregation\. Unit: Count Can be used to monitor: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html) Some ways to use the data: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html)  | 
|  `glue.driver.aggregate.numCompletedTasks` |  The number of completed tasks in the job\. Valid dimensions: `JobName` \(the name of the AWS Glue Job\), `JobRunId` \(the JobRun ID\. or `ALL`\), and `Type` \(count\)\. Valid Statistics: SUM\. This metric is a delta value from the last reported value, so on the AWS Glue Metrics Dashboard, a SUM statistic is used for aggregation\. Unit: Count Can be used to monitor: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html)  | 
|  `glue.driver.aggregate.numFailedTasks` |  The number of failed tasks\. Valid dimensions: `JobName` \(the name of the AWS Glue Job\), `JobRunId` \(the JobRun ID\. or `ALL`\), and `Type` \(count\)\. Valid Statistics: SUM\. This metric is a delta value from the last reported value, so on the AWS Glue Metrics Dashboard, a SUM statistic is used for aggregation\. Unit: Count Can be used to monitor: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html) The data can be used to set alarms for increased failures that might suggest abnormalities in data, cluster or scripts\.  | 
|  `glue.driver.aggregate.numKilledTasks` |  The number of tasks killed\. Valid dimensions: `JobName` \(the name of the AWS Glue Job\), `JobRunId` \(the JobRun ID\. or `ALL`\), and `Type` \(count\)\. Valid Statistics: SUM\. This metric is a delta value from the last reported value, so on the AWS Glue Metrics Dashboard, a SUM statistic is used for aggregation\. Unit: Count Can be used to monitor: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html) Some ways to use the data: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html)  | 
|  `glue.driver.aggregate.recordsRead` |  The number of records read from all data sources by all completed Spark tasks running in all executors\. Valid dimensions: `JobName` \(the name of the AWS Glue Job\), `JobRunId` \(the JobRun ID\. or `ALL`\), and `Type` \(count\)\. Valid Statistics: SUM\. This metric is a delta value from the last reported value, so on the AWS Glue Metrics Dashboard, a SUM statistic is used for aggregation\. Unit: Count Can be used to monitor: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html) This metric can be used in a similar way to the `glue.ALL.s3.filesystem.read_bytes` metric, with the difference that this metric is updated at the end of a Spark task\.  | 
|   `glue.driver.aggregate.shuffleBytesWritten` |  The number of bytes written by all executors to shuffle data between them since the previous report \(aggregated by the AWS Glue Metrics Dashboard as the number of bytes written for this purpose during the previous minute\)\. Valid dimensions: `JobName` \(the name of the AWS Glue Job\), `JobRunId` \(the JobRun ID\. or `ALL`\), and `Type` \(count\)\. Valid Statistics: SUM\. This metric is a delta value from the last reported value, so on the AWS Glue Metrics Dashboard, a SUM statistic is used for aggregation\. Unit: Bytes Can be used to monitor: Data shuffle in jobs \(large joins, groupBy, repartition, coalesce\)\. Some ways to use the data: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html)  | 
|   `glue.driver.aggregate.shuffleLocalBytesRead` |  The number of bytes read by all executors to shuffle data between them since the previous report \(aggregated by the AWS Glue Metrics Dashboard as the number of bytes read for this purpose during the previous minute\)\. Valid dimensions: `JobName` \(the name of the AWS Glue Job\), `JobRunId` \(the JobRun ID\. or `ALL`\), and `Type` \(count\)\. Valid Statistics: SUM\. This metric is a delta value from the last reported value, so on the AWS Glue Metrics Dashboard, a SUM statistic is used for aggregation\. Unit: Bytes Can be used to monitor: Data shuffle in jobs \(large joins, groupBy, repartition, coalesce\)\. Some ways to use the data: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html)  | 
|  `glue.driver.BlockManager.disk.diskSpaceUsed_MB` |  The number of megabytes of disk space used across all executors\. Valid dimensions: `JobName` \(the name of the AWS Glue Job\), `JobRunId` \(the JobRun ID\. or `ALL`\), and `Type` \(gauge\)\. Valid Statistics: Average\. This is a Spark metric, reported as an absolute value\. Unit: Megabytes Can be used to monitor: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html) Some ways to use the data: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html)  | 
|   `glue.driver.ExecutorAllocationManager.executors.numberAllExecutors` |  The number of actively running job executors\. Valid dimensions: `JobName` \(the name of the AWS Glue Job\), `JobRunId` \(the JobRun ID\. or `ALL`\), and `Type` \(gauge\)\. Valid Statistics: Average\. This is a Spark metric, reported as an absolute value\. Unit: Count Can be used to monitor: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html) Some ways to use the data: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html)  | 
|   `glue.driver.ExecutorAllocationManager.executors.numberMaxNeededExecutors` |  The number of maximum \(actively running and pending\) job executors needed to satisfy the current load\. Valid dimensions: `JobName` \(the name of the AWS Glue Job\), `JobRunId` \(the JobRun ID\. or `ALL`\), and `Type` \(gauge\)\. Valid Statistics: Maximum\. This is a Spark metric, reported as an absolute value\. Unit: Count Can be used to monitor: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html) Some ways to use the data: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html)  | 
|   `glue.driver.jvm.heap.usage`  `glue.`*executorId*`.jvm.heap.usage`  `glue.ALL.jvm.heap.usage`  |  The fraction of memory used by the JVM heap for this driver \(scale: 0\-1\) for driver, executor identified by executorId, or ALL executors\. Valid dimensions: `JobName` \(the name of the AWS Glue Job\), `JobRunId` \(the JobRun ID\. or `ALL`\), and `Type` \(gauge\)\. Valid Statistics: Average\. This is a Spark metric, reported as an absolute value\. Unit: Percentage Can be used to monitor: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html) Some ways to use the data: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html)  | 
|  `glue.driver.jvm.heap.used`  `glue.`*executorId*`.jvm.heap.used`  `glue.ALL.jvm.heap.used`  |  The number of memory bytes used by the JVM heap for the driver, the executor identified by *executorId*, or ALL executors\. Valid dimensions: `JobName` \(the name of the AWS Glue Job\), `JobRunId` \(the JobRun ID\. or `ALL`\), and `Type` \(gauge\)\. Valid Statistics: Average\. This is a Spark metric, reported as an absolute value\. Unit: Bytes Can be used to monitor: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html) Some ways to use the data: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html)  | 
|   `glue.driver.s3.filesystem.read_bytes`  `glue.`*executorId*`.s3.filesystem.read_bytes`  `glue.ALL.s3.filesystem.read_bytes`  |  The number of bytes read from Amazon S3 by the driver, an executor identified by *executorId*, or ALL executors since the previous report \(aggregated by the AWS Glue Metrics Dashboard as the number of bytes read during the previous minute\)\. Valid dimensions: `JobName`, `JobRunId`, and `Type` \(gauge\)\. Valid Statistics: SUM\. This metric is a delta value from the last reported value, so on the AWS Glue Metrics Dashboard a SUM statistic is used for aggregation\. The area under the curve on the AWS Glue Metrics Dashboard can be used to visually compare bytes read by two different job runs\. Unit: Bytes\. Can be used to monitor: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html) Resulting data can be used for: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html)  | 
|   `glue.driver.s3.filesystem.write_bytes`  `glue.`*executorId*`.s3.filesystem.write_bytes`  `glue.ALL.s3.filesystem.write_bytes`  |  The number of bytes written to Amazon S3 by the driver, an executor identified by *executorId*, or ALL executors since the previous report \(aggregated by the AWS Glue Metrics Dashboard as the number of bytes written during the previous minute\)\. Valid dimensions: `JobName`, `JobRunId`, and `Type` \(gauge\)\. Valid Statistics: SUM\. This metric is a delta value from the last reported value, so on the AWS Glue Metrics Dashboard a SUM statistic is used for aggregation\. The area under the curve on the AWS Glue Metrics Dashboard can be used to visually compare bytes written by two different job runs\. Unit: Bytes Can be used to monitor: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html) Some ways to use the data: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html)  | 
|   `glue.driver.system.cpuSystemLoad`  `glue.`*executorId*`.system.cpuSystemLoad`  `glue.ALL.system.cpuSystemLoad`  |  The fraction of CPU system load used \(scale: 0\-1\) by the driver, an executor identified by *executorId*, or ALL executors\. Valid dimensions: `JobName` \(the name of the AWS Glue Job\), `JobRunId` \(the JobRun ID\. or `ALL`\), and `Type` \(gauge\)\. Valid Statistics: Average\. This metric is reported as an absolute value\. Unit: Percentage Can be used to monitor: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html) Some ways to use the data: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/glue-metrics-dimensions.html)  | 

## Dimensions for AWS Glue Metrics<a name="awsglue-metricdimensions"></a>

AWS Glue metrics use the AWS Glue namespace and provide metrics for the following dimensions:


| Dimension | Description | 
| --- | --- | 
|  `JobName`  |  Filters for metrics of all job runs of a specific job\.  | 
|  `JobRunId`  |  Filters for metrics of a specific job run\.  | 
|  `Type`  |  Filters for metrics of a specified type\.  | 