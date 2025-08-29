# Accelerate

```java
AccelerateController accelerateController = client.getAccelerateController();
```

## Class Name

`AccelerateController`

## Methods

* [Bucket Accelerate Configuration](../../doc/controllers/accelerate.md#bucket-accelerate-configuration)
* [Bucket Accelerate Configuration 1](../../doc/controllers/accelerate.md#bucket-accelerate-configuration-1)
* [Get Bucket Accelerate Configuration](../../doc/controllers/accelerate.md#get-bucket-accelerate-configuration)


# Bucket Accelerate Configuration

Sets the accelerate configuration of an existing bucket. Amazon S3 Transfer Acceleration is a bucket-level feature that enables you to perform faster data transfers to Amazon S3.

```java
CompletableFuture<DynamicResponse> bucketAccelerateConfigurationAsync(
    final String accelerate,
    final String body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accelerate` | `String` | Query, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String accelerate = "accelerate6";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<AccelerateConfiguration xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n   <Status>Enabled</Status>\n</AccelerateConfiguration>";
String bucket = "bucket2";

accelerateController.bucketAccelerateConfigurationAsync(accelerate, body, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Bucket Accelerate Configuration 1

Sets the accelerate configuration of an existing bucket. Amazon S3 Transfer Acceleration is a bucket-level feature that enables you to perform faster data transfers to Amazon S3.

```java
CompletableFuture<ListBucketResult> bucketAccelerateConfiguration1Async(
    final String accelerate,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accelerate` | `String` | Query, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

[`ListBucketResult`](../../doc/models/list-bucket-result.md)

## Example Usage

```java
String accelerate = "accelerate6";
String bucket = "bucket2";

accelerateController.bucketAccelerateConfiguration1Async(accelerate, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response *(as XML)*

```xml
<ListBucketResult>
  <Name>working-demo-2</Name>
  <Prefix></Prefix>
  <Marker></Marker>
  <MaxKeys>1000</MaxKeys>
  <IsTruncated>false</IsTruncated>
</ListBucketResult>
```


# Get Bucket Accelerate Configuration

This implementation of the GET operation uses the accelerate subresource to return the Transfer Acceleration state of a bucket, which is either Enabled or Suspended. Amazon S3 Transfer Acceleration is a bucket-level feature that enables you to perform faster data transfers to and from Amazon S3.

```java
CompletableFuture<Void> getBucketAccelerateConfigurationAsync(
    final String accelerate,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accelerate` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String accelerate = "accelerate6";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

accelerateController.getBucketAccelerateConfigurationAsync(accelerate, xAmzContentSha256, bucket).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

