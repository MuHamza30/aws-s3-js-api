# Legal Hold

```java
LegalHoldController legalHoldController = client.getLegalHoldController();
```

## Class Name

`LegalHoldController`

## Methods

* [Legal Hold](../../doc/controllers/legal-hold.md#legal-hold)
* [Legal Hold 1](../../doc/controllers/legal-hold.md#legal-hold-1)


# Legal Hold

Gets an object's current Legal Hold status. For more information, see Locking Objects.

```java
CompletableFuture<Void> legalHoldAsync(
    final String legalHold,
    final String xAmzContentSha256,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `legalHold` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String legalHold = "legal-hold2";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";
String key = "key0";

legalHoldController.legalHoldAsync(legalHold, xAmzContentSha256, bucket, key).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Legal Hold 1

Gets an object's current Legal Hold status. For more information, see Locking Objects.

```java
CompletableFuture<Void> legalHold1Async(
    final String legalHold,
    final String contentMD5,
    final String body,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `legalHold` | `String` | Query, Required | - |
| `contentMD5` | `String` | Header, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String legalHold = "legal-hold2";
String contentMD5 = "{{contentMD5}}";
String body = "<LegalHold xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n   <Status>ON</Status>\n</LegalHold>";
String bucket = "bucket2";
String key = "key0";

legalHoldController.legalHold1Async(legalHold, contentMD5, body, bucket, key).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

