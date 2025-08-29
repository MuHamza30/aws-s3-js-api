# Versioning

```java
VersioningController versioningController = client.getVersioningController();
```

## Class Name

`VersioningController`

## Methods

* [Bucket Versioning](../../doc/controllers/versioning.md#bucket-versioning)
* [Bucket Versioning 1](../../doc/controllers/versioning.md#bucket-versioning-1)


# Bucket Versioning

Returns the versioning state of a bucket.

```java
CompletableFuture<String> bucketVersioningAsync(
    final String versioning,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `versioning` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`String`

## Example Usage

```java
String versioning = "versioning8";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

versioningController.bucketVersioningAsync(versioning, xAmzContentSha256, bucket).thenAccept(result -> {
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
"<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<VersioningConfiguration xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><Status>Enabled</Status></VersioningConfiguration>"
```


# Bucket Versioning 1

Sets the versioning state of an existing bucket. To set the versioning state, you must be the bucket owner.

```java
CompletableFuture<DynamicResponse> bucketVersioning1Async(
    final String versioning,
    final String contentMD5,
    final String body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `versioning` | `String` | Query, Required | - |
| `contentMD5` | `String` | Header, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String versioning = "versioning8";
String contentMD5 = "{{contentMD5}}";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<VersioningConfiguration xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><Status>Enabled</Status></VersioningConfiguration>";
String bucket = "bucket2";

versioningController.bucketVersioning1Async(versioning, contentMD5, body, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

