# Public Access Block

```java
PublicAccessBlockController publicAccessBlockController = client.getPublicAccessBlockController();
```

## Class Name

`PublicAccessBlockController`

## Methods

* [Public Access Block](../../doc/controllers/public-access-block.md#public-access-block)
* [Public Access Block 1](../../doc/controllers/public-access-block.md#public-access-block-1)
* [Public Access Block 2](../../doc/controllers/public-access-block.md#public-access-block-2)


# Public Access Block

Retrieves the PublicAccessBlock configuration for an Amazon S3 bucket. In order to use this operation, you must have the s3:GetBucketPublicAccessBlock permission. For more information about Amazon S3 permissions, see Specifying Permissions in a Policy.

```java
CompletableFuture<Void> publicAccessBlockAsync(
    final String publicAccessBlock,
    final String xAmzContentSha256)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `publicAccessBlock` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |

## Response Type

`void`

## Example Usage

```java
String publicAccessBlock = "publicAccessBlock0";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";

publicAccessBlockController.publicAccessBlockAsync(publicAccessBlock, xAmzContentSha256).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Public Access Block 1

Retrieves the PublicAccessBlock configuration for an Amazon S3 bucket. In order to use this operation, you must have the s3:GetBucketPublicAccessBlock permission. For more information about Amazon S3 permissions, see Specifying Permissions in a Policy.

```java
CompletableFuture<Void> publicAccessBlock1Async(
    final String publicAccessBlock,
    final String xAmzContentSha256)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `publicAccessBlock` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |

## Response Type

`void`

## Example Usage

```java
String publicAccessBlock = "publicAccessBlock0";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";

publicAccessBlockController.publicAccessBlock1Async(publicAccessBlock, xAmzContentSha256).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Public Access Block 2

Removes the PublicAccessBlock configuration for an Amazon S3 bucket. In order to use this operation, you must have the s3:PutBucketPublicAccessBlock permission.

```java
CompletableFuture<Void> publicAccessBlock2Async(
    final String publicAccessBlock,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `publicAccessBlock` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String publicAccessBlock = "publicAccessBlock0";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

publicAccessBlockController.publicAccessBlock2Async(publicAccessBlock, xAmzContentSha256, bucket).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

