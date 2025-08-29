# Logging

```java
LoggingController loggingController = client.getLoggingController();
```

## Class Name

`LoggingController`

## Methods

* [Bucket Logging](../../doc/controllers/logging.md#bucket-logging)
* [Bucket Logging 1](../../doc/controllers/logging.md#bucket-logging-1)


# Bucket Logging

Returns the logging status of a bucket and the permissions users have to view and modify that status. To use GET, you must be the bucket owner.

```java
CompletableFuture<String> bucketLoggingAsync(
    final String logging,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `logging` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`String`

## Example Usage

```java
String logging = "logging0";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

loggingController.bucketLoggingAsync(logging, xAmzContentSha256, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Bucket Logging 1

Set the logging parameters for a bucket and to specify permissions for who can view and modify the logging parameters. All logs are saved to buckets in the same AWS Region as the source bucket. To set the logging status of a bucket, you must be the bucket owner.

```java
CompletableFuture<Void> bucketLogging1Async(
    final String logging,
    final String contentMD5,
    final String body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `logging` | `String` | Query, Required | - |
| `contentMD5` | `String` | Header, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String logging = "logging0";
String contentMD5 = "{{contentMD5}}";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<BucketLoggingStatus xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n   <LoggingEnabled>\n      <TargetBucket>working-demo-2</TargetBucket>\n   </LoggingEnabled>\n</BucketLoggingStatus>";
String bucket = "bucket2";

loggingController.bucketLogging1Async(logging, contentMD5, body, bucket).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

