# Lifecycle

```java
LifecycleController lifecycleController = client.getLifecycleController();
```

## Class Name

`LifecycleController`

## Methods

* [Bucket Lifecycle](../../doc/controllers/lifecycle.md#bucket-lifecycle)
* [Delete Bucket Lifecycle](../../doc/controllers/lifecycle.md#delete-bucket-lifecycle)
* [Bucket Lifecycle 1](../../doc/controllers/lifecycle.md#bucket-lifecycle-1)


# Bucket Lifecycle

Returns the lifecycle configuration information set on the bucket. For information about lifecycle configuration, see Object Lifecycle Management.

```java
CompletableFuture<String> bucketLifecycleAsync(
    final String lifecycle,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `lifecycle` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`String`

## Example Usage

```java
String lifecycle = "lifecycle8";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

lifecycleController.bucketLifecycleAsync(lifecycle, xAmzContentSha256, bucket).thenAccept(result -> {
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
"<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<LifecycleConfiguration xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><Rule><ID>/my</ID><Filter><Tag><Key>test</Key><Value></Value></Tag></Filter><Status>Enabled</Status><Expiration><Days>365</Days></Expiration></Rule></LifecycleConfiguration>"
```


# Delete Bucket Lifecycle

Deletes the lifecycle configuration from the specified bucket. Amazon S3 removes all the lifecycle configuration rules in the lifecycle subresource associated with the bucket. Your objects never expire, and Amazon S3 no longer automatically deletes any objects on the basis of rules contained in the deleted lifecycle configuration.

```java
CompletableFuture<DynamicResponse> deleteBucketLifecycleAsync(
    final String lifecycle,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `lifecycle` | `String` | Query, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String lifecycle = "lifecycle8";
String bucket = "bucket2";

lifecycleController.deleteBucketLifecycleAsync(lifecycle, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Bucket Lifecycle 1

Creates a new lifecycle configuration for the bucket or replaces an existing lifecycle configuration.

```java
CompletableFuture<DynamicResponse> bucketLifecycle1Async(
    final String lifecycle,
    final String contentMD5,
    final String body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `lifecycle` | `String` | Query, Required | - |
| `contentMD5` | `String` | Header, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String lifecycle = "lifecycle8";
String contentMD5 = "{{contentMD5}}";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<LifecycleConfiguration xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><Rule><ID>/my</ID><Filter><Tag><Key>test</Key><Value></Value></Tag></Filter><Status>Enabled</Status><Expiration><Days>365</Days></Expiration></Rule></LifecycleConfiguration>";
String bucket = "bucket2";

lifecycleController.bucketLifecycle1Async(lifecycle, contentMD5, body, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

