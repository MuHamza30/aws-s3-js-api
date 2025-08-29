# Misc

```java
MiscController miscController = client.getMiscController();
```

## Class Name

`MiscController`


# Root

```java
CompletableFuture<Void> rootAsync(
    final String xAmzContentSha256)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `xAmzContentSha256` | `String` | Header, Required | - |

## Response Type

`void`

## Example Usage

```java
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";

miscController.rootAsync(xAmzContentSha256).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

