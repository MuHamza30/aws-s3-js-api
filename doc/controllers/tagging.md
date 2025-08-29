# Tagging

```java
TaggingController taggingController = client.getTaggingController();
```

## Class Name

`TaggingController`

## Methods

* [Bucket Tagging](../../doc/controllers/tagging.md#bucket-tagging)
* [Bucket Tagging 1](../../doc/controllers/tagging.md#bucket-tagging-1)
* [Delete Bucket Tagging](../../doc/controllers/tagging.md#delete-bucket-tagging)
* [Object Tagging](../../doc/controllers/tagging.md#object-tagging)
* [Tagging](../../doc/controllers/tagging.md#tagging)
* [Delete Object Tagging](../../doc/controllers/tagging.md#delete-object-tagging)


# Bucket Tagging

Returns the tag set associated with the bucket.

```java
CompletableFuture<Void> bucketTaggingAsync(
    final String tagging,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tagging` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String tagging = "tagging6";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

taggingController.bucketTaggingAsync(tagging, xAmzContentSha256, bucket).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Bucket Tagging 1

Sets the tags for a bucket.

```java
CompletableFuture<DynamicResponse> bucketTagging1Async(
    final String tagging,
    final String contentMD5,
    final String body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tagging` | `String` | Query, Required | - |
| `contentMD5` | `String` | Header, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String tagging = "tagging6";
String contentMD5 = "{{contentMD5}}";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<Tagging xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n   <TagSet>\n      <Tag>\n         <Key>Test 123</Key>\n         <Value>Test 123</Value>\n      </Tag>\n   </TagSet>\n</Tagging>";
String bucket = "bucket2";

taggingController.bucketTagging1Async(tagging, contentMD5, body, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Delete Bucket Tagging

Deletes the tags from the bucket.

```java
CompletableFuture<DynamicResponse> deleteBucketTaggingAsync(
    final String tagging,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tagging` | `String` | Query, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String tagging = "tagging6";
String bucket = "bucket2";

taggingController.deleteBucketTaggingAsync(tagging, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Object Tagging

Returns the tag-set of an object. You send the GET request against the tagging subresource associated with the object.

```java
CompletableFuture<String> objectTaggingAsync(
    final String tagging,
    final String xAmzContentSha256,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tagging` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`String`

## Example Usage

```java
String tagging = "tagging6";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";
String key = "key0";

taggingController.objectTaggingAsync(tagging, xAmzContentSha256, bucket, key).thenAccept(result -> {
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
"<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<Tagging xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><TagSet><Tag><Key>Test</Key><Value>Test</Value></Tag></TagSet></Tagging>"
```


# Tagging

Returns the tag-set of an object. You send the GET request against the tagging subresource associated with the object.

```java
CompletableFuture<DynamicResponse> taggingAsync(
    final String tagging,
    final String body,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tagging` | `String` | Query, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String tagging = "tagging6";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<Tagging xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n   <TagSet>\n      <Tag>\n         <Key>Test</Key>\n         <Value>Test</Value>\n      </Tag>\n   </TagSet>\n</Tagging>";
String bucket = "bucket2";
String key = "key0";

taggingController.taggingAsync(tagging, body, bucket, key).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Delete Object Tagging

Removes the entire tag set from the specified object. For more information about managing object tags, see Object Tagging.

```java
CompletableFuture<DynamicResponse> deleteObjectTaggingAsync(
    final String tagging,
    final String xAmzContentSha256,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tagging` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String tagging = "tagging6";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";
String key = "key0";

taggingController.deleteObjectTaggingAsync(tagging, xAmzContentSha256, bucket, key).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

