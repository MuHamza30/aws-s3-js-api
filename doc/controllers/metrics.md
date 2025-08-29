# Metrics

```java
MetricsController metricsController = client.getMetricsController();
```

## Class Name

`MetricsController`

## Methods

* [Bucket Metrics Configuration](../../doc/controllers/metrics.md#bucket-metrics-configuration)
* [Bucket Metrics Configuration 1](../../doc/controllers/metrics.md#bucket-metrics-configuration-1)
* [List Bucket Metrics Configurations](../../doc/controllers/metrics.md#list-bucket-metrics-configurations)
* [Delete Bucket Metrics Configuration](../../doc/controllers/metrics.md#delete-bucket-metrics-configuration)


# Bucket Metrics Configuration

Gets a metrics configuration (specified by the metrics configuration ID) from the bucket. Note that this doesn't include the daily storage metrics.

```java
CompletableFuture<String> bucketMetricsConfigurationAsync(
    final String metrics,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `metrics` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`String`

## Example Usage

```java
String metrics = "metrics8";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

metricsController.bucketMetricsConfigurationAsync(metrics, xAmzContentSha256, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response

```
"<?xml version=\"1.0\" encoding=\"UTF-8\"?><ListMetricsConfigurationsResult xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><IsTruncated>false</IsTruncated></ListMetricsConfigurationsResult>"
```


# Bucket Metrics Configuration 1

Sets a metrics configuration (specified by the metrics configuration ID) for the bucket. You can have up to 1,000 metrics configurations per bucket. If you're updating an existing metrics configuration, note that this is a full replacement of the existing metrics configuration. If you don't include the elements you want to keep, they are erased.

```java
CompletableFuture<Void> bucketMetricsConfiguration1Async(
    final String metrics,
    final String id,
    final String body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `metrics` | `String` | Query, Required | - |
| `id` | `String` | Query, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String metrics = "metrics8";
String id = "{{Id}}";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<MetricsConfiguration xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n   <Id>test1</Id>\n   <Filter>\n      <And>\n         <Prefix>string</Prefix>\n         <Tag>\n            <Key>string</Key>\n            <Value>string</Value>\n         </Tag>\n      </And>\n      <Prefix>string</Prefix>\n      <Tag>\n         <Key>string</Key>\n         <Value>string</Value>\n      </Tag>\n   </Filter>\n</MetricsConfiguration>";
String bucket = "bucket2";

metricsController.bucketMetricsConfiguration1Async(metrics, id, body, bucket).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# List Bucket Metrics Configurations

Lists the metrics configurations for the bucket. The metrics configurations are only for the request metrics of the bucket and do not provide information on daily storage metrics. You can have up to 1,000 configurations per bucket.

```java
CompletableFuture<String> listBucketMetricsConfigurationsAsync(
    final String metrics,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `metrics` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`String`

## Example Usage

```java
String metrics = "metrics8";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

metricsController.listBucketMetricsConfigurationsAsync(metrics, xAmzContentSha256, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response

```
"<?xml version=\"1.0\" encoding=\"UTF-8\"?><ListMetricsConfigurationsResult xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><IsTruncated>false</IsTruncated></ListMetricsConfigurationsResult>"
```


# Delete Bucket Metrics Configuration

Deletes a metrics configuration for the Amazon CloudWatch request metrics (specified by the metrics configuration ID) from the bucket. Note that this doesn't include the daily storage metrics.

```java
CompletableFuture<Void> deleteBucketMetricsConfigurationAsync(
    final String metrics,
    final String id,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `metrics` | `String` | Query, Required | - |
| `id` | `String` | Query, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String metrics = "metrics8";
String id = "test";
String bucket = "bucket2";

metricsController.deleteBucketMetricsConfigurationAsync(metrics, id, bucket).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

