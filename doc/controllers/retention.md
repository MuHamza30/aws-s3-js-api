# Retention

```java
RetentionController retentionController = client.getRetentionController();
```

## Class Name

`RetentionController`

## Methods

* [Retention](../../doc/controllers/retention.md#retention)
* [Retention 1](../../doc/controllers/retention.md#retention-1)


# Retention

Retrieves an object's retention settings. For more information, see Locking Objects.

```java
CompletableFuture<Void> retentionAsync(
    final String retention,
    final String xAmzContentSha256,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `retention` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String retention = "retention2";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";
String key = "key0";

retentionController.retentionAsync(retention, xAmzContentSha256, bucket, key).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Retention 1

Retrieves an object's retention settings. For more information, see Locking Objects.

```java
CompletableFuture<Void> retention1Async(
    final String retention,
    final String xAmzContentSha256,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `retention` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String retention = "retention2";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";
String key = "key0";

retentionController.retention1Async(retention, xAmzContentSha256, bucket, key).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

