# Encryption

```java
EncryptionController encryptionController = client.getEncryptionController();
```

## Class Name

`EncryptionController`

## Methods

* [Bucket Encryption](../../doc/controllers/encryption.md#bucket-encryption)
* [Bucket Encryption 1](../../doc/controllers/encryption.md#bucket-encryption-1)
* [Delete Bucket Encryption](../../doc/controllers/encryption.md#delete-bucket-encryption)


# Bucket Encryption

Returns the default encryption configuration for an Amazon S3 bucket. For information about the Amazon S3 default encryption feature, see Amazon S3 Default Bucket Encryption.

```java
CompletableFuture<String> bucketEncryptionAsync(
    final String encryption,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `encryption` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`String`

## Example Usage

```java
String encryption = "encryption4";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

encryptionController.bucketEncryptionAsync(encryption, xAmzContentSha256, bucket).thenAccept(result -> {
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
"<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<ServerSideEncryptionConfiguration xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><Rule><ApplyServerSideEncryptionByDefault><SSEAlgorithm>AES256</SSEAlgorithm></ApplyServerSideEncryptionByDefault></Rule></ServerSideEncryptionConfiguration>"
```


# Bucket Encryption 1

This implementation of the PUT operation uses the encryption subresource to set the default encryption state of an existing bucket.

```java
CompletableFuture<DynamicResponse> bucketEncryption1Async(
    final String encryption,
    final String body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `encryption` | `String` | Query, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String encryption = "encryption4";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<ServerSideEncryptionConfiguration xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n   <Rule><ApplyServerSideEncryptionByDefault><SSEAlgorithm>AES256</SSEAlgorithm></ApplyServerSideEncryptionByDefault></Rule>\n</ServerSideEncryptionConfiguration>";
String bucket = "bucket2";

encryptionController.bucketEncryption1Async(encryption, body, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Delete Bucket Encryption

This implementation of the DELETE operation removes default encryption from the bucket.

```java
CompletableFuture<DynamicResponse> deleteBucketEncryptionAsync(
    final String encryption,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `encryption` | `String` | Query, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String encryption = "encryption4";
String bucket = "bucket2";

encryptionController.deleteBucketEncryptionAsync(encryption, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

