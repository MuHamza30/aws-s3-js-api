# Versions

```java
VersionsController versionsController = client.getVersionsController();
```

## Class Name

`VersionsController`


# Object Versions

Returns metadata about all of the versions of objects in a bucket. You can also use request parameters as selection criteria to return metadata about a subset of all the object versions.

```java
CompletableFuture<ListVersionsResult> objectVersionsAsync(
    final String versions,
    final String delimiter,
    final String encodingType,
    final String keyMarker,
    final String maxKeys,
    final String prefix,
    final String versionIdMarker,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `versions` | `String` | Query, Required | - |
| `delimiter` | `String` | Query, Required | - |
| `encodingType` | `String` | Query, Required | - |
| `keyMarker` | `String` | Query, Required | - |
| `maxKeys` | `String` | Query, Required | - |
| `prefix` | `String` | Query, Required | - |
| `versionIdMarker` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

[`ListVersionsResult`](../../doc/models/list-versions-result.md)

## Example Usage

```java
String versions = "versions0";
String delimiter = "{{Delimiter}}";
String encodingType = "{{EncodingType}}";
String keyMarker = "{{KeyMarker}}";
String maxKeys = "{{MaxKeys}}";
String prefix = "{{Prefix}}";
String versionIdMarker = "{{VersionIdMarker}}";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

versionsController.objectVersionsAsync(versions, delimiter, encodingType, keyMarker, maxKeys, prefix, versionIdMarker, xAmzContentSha256, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

