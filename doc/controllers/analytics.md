# Analytics

```java
AnalyticsController analyticsController = client.getAnalyticsController();
```

## Class Name

`AnalyticsController`

## Methods

* [Bucket Analytics](../../doc/controllers/analytics.md#bucket-analytics)
* [Bucket Analytics Configurations](../../doc/controllers/analytics.md#bucket-analytics-configurations)
* [Bucket Analytics Configurations 1](../../doc/controllers/analytics.md#bucket-analytics-configurations-1)
* [Delete Bucket Analytics Configuration](../../doc/controllers/analytics.md#delete-bucket-analytics-configuration)


# Bucket Analytics

This implementation of the GET operation returns an analytics configuration (identified by the analytics configuration ID) from the bucket.

```java
CompletableFuture<String> bucketAnalyticsAsync(
    final String analytics,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `analytics` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`String`

## Example Usage

```java
String analytics = "analytics2";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

analyticsController.bucketAnalyticsAsync(analytics, xAmzContentSha256, bucket).thenAccept(result -> {
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
"<ListBucketAnalyticsConfigurationsResult xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><IsTruncated>false</IsTruncated></ListBucketAnalyticsConfigurationsResult>"
```


# Bucket Analytics Configurations

Lists the analytics configurations for the bucket. You can have up to 1,000 analytics configurations per bucket.

```java
CompletableFuture<String> bucketAnalyticsConfigurationsAsync(
    final String analytics,
    final String id,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `analytics` | `String` | Query, Required | - |
| `id` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`String`

## Example Usage

```java
String analytics = "analytics2";
String id = "test";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

analyticsController.bucketAnalyticsConfigurationsAsync(analytics, id, xAmzContentSha256, bucket).thenAccept(result -> {
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
"<ListBucketAnalyticsConfigurationsResult xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><IsTruncated>false</IsTruncated></ListBucketAnalyticsConfigurationsResult>"
```


# Bucket Analytics Configurations 1

Sets an analytics configuration for the bucket (specified by the analytics configuration ID). You can have up to 1,000 analytics configurations per bucket.

```java
CompletableFuture<Void> bucketAnalyticsConfigurations1Async(
    final String analytics,
    final String id,
    final String body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `analytics` | `String` | Query, Required | - |
| `id` | `String` | Query, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String analytics = "analytics2";
String id = "test2";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<AnalyticsConfiguration xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n   <Id>test</Id>\n   <Filter>\n      <And>\n         <Prefix>test/</Prefix>\n         <Tag>\n            <Key>string</Key>\n            <Value>string</Value>\n         </Tag>\n      </And>\n      <Prefix>string</Prefix>\n      <Tag>\n         <Key>string</Key>\n         <Value>string</Value>\n      </Tag>\n   </Filter>\n   <StorageClassAnalysis>\n      <DataExport>\n         <Destination>\n            <S3BucketDestination>\n               <Bucket>arn:aws:s3:::working-demo-2</Bucket>\n               <Format>CSV</Format>\n               <Prefix>destination-prefix</Prefix>\n            </S3BucketDestination>\n         </Destination>\n         <OutputSchemaVersion>string</OutputSchemaVersion>\n      </DataExport>\n   </StorageClassAnalysis>\n</AnalyticsConfiguration>";
String bucket = "bucket2";

analyticsController.bucketAnalyticsConfigurations1Async(analytics, id, body, bucket).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Delete Bucket Analytics Configuration

Deletes an analytics configuration for the bucket (specified by the analytics configuration ID).

```java
CompletableFuture<DynamicResponse> deleteBucketAnalyticsConfigurationAsync(
    final String analytics,
    final String id,
    final String body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `analytics` | `String` | Query, Required | - |
| `id` | `String` | Query, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String analytics = "analytics2";
String id = "test";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<CreateBucketConfiguration xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n   <LocationConstraint>us-west-1</LocationConstraint>\n</CreateBucketConfiguration>";
String bucket = "bucket2";

analyticsController.deleteBucketAnalyticsConfigurationAsync(analytics, id, body, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

