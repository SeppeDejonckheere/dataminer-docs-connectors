---
uid: Connector_help_Amazon_AWS_CloudWatch_-_Kinesis_Data_Streams
---

# Amazon AWS CloudWatch - Kinesis Data Streams

CloudWatch can be used to monitor the Kinesis Data Streams Service. Amazon Kinesis is used to collect, process, and analyze streaming data in real time, such as video, audio, application logs, website clickstreams and IoT telemetry data for machine learning, analytics and other applications. It is possible to monitor metrics on both service stream and shard level.

## About

### Product Info

| Range     | Supported Firmware     |
|-----------|------------------------|
| 1.0.0.x   | 20100801               |

### System Info

| Range     | DCF Integration     | Cassandra Compliant     | Linked Components     | Exported Components     |
|-----------|---------------------|-------------------------|-----------------------|-------------------------|
| 1.0.0.x   | No                  | Yes                     | \-                    | \-                      |

## Configuration

### Connections

#### Virtual Connection

This connector uses a virtual connection and does not require any input during element creation.

## How to Use

This connector is automatically generated by the connector Amazon AWS CloudWatch, range 1.0.0.x.

The element created with this connector consists of the following data pages:

- **General**: This page contains the **Entry ID**, which is a unique identifier for this service. The **Entry Type** provides more insight in the different parts that the **Entry ID** consists of. The **Polling Interval** can be modified on this page and the **Entry Status** indicates if the service entry is still present. With the **Force Polling** button, you can poll the metrics immediately without having to wait until the interval time has elapsed.
- **Get Records**: This page contains all metrics for the Get Records calls, used to read data records sequentially.
- **Put Record**: This page contains the metrics for the Put Record calls, used to write a single data record into an Amazon Kinesis data stream.
- **Put Records**: This page contains the metrics for the Put Records calls, used to write multiple data records into an Amazon Kinesis stream in a single call.
- **Shard Subscription**: This page contains all metrics related to the Shard Subscription, an HTTP/2 connection between the consumer and the specified AWS shard ID.

On any of the metrics pages mentioned above, polling of the appropriate metrics can be enabled via the **Config Poll** page button. It is not possible to set the Poll parameter to *Enabled* for metric parameters that have the *N/A* value. These *N/A* metrics are not present in the provided metrics list for this instance and hence their Poll parameter will remain *Disabled*.
