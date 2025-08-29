# Location

```java
LocationController locationController = client.getLocationController();
```

## Class Name

`LocationController`


# Bucket Location

Returns the region the bucket resides in. You set the bucket's region using the LocationConstraint request parameter in a CreateBucket request. For more information, see CreateBucket.

```java
CompletableFuture<String> bucketLocationAsync(
    final String location,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `location` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`String`

## Example Usage

```java
String location = "location4";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

locationController.bucketLocationAsync(location, xAmzContentSha256, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

