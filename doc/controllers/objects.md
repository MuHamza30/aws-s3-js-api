# Objects

```java
ObjectsController objectsController = client.getObjectsController();
```

## Class Name

`ObjectsController`

## Methods

* [Object](../../doc/controllers/objects.md#object)
* [Objects V1](../../doc/controllers/objects.md#objects-v1)
* [Objects V2](../../doc/controllers/objects.md#objects-v2)
* [Object 1](../../doc/controllers/objects.md#object-1)
* [Parts](../../doc/controllers/objects.md#parts)
* [Copy Object](../../doc/controllers/objects.md#copy-object)
* [Delete Object](../../doc/controllers/objects.md#delete-object)
* [Delete Objects](../../doc/controllers/objects.md#delete-objects)


# Object

The HEAD operation retrieves metadata from an object without returning the object itself. This operation is useful if you're only interested in an object's metadata. To use HEAD, you must have READ access to the object.

```java
CompletableFuture<Void> objectAsync(
    final String partNumber,
    final String versionId,
    final String xAmzContentSha256,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `partNumber` | `String` | Query, Required | - |
| `versionId` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String partNumber = "PartNumber";
String versionId = "VersionId";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";
String key = "key0";

objectsController.objectAsync(partNumber, versionId, xAmzContentSha256, bucket, key).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |


# Objects V1

Returns some or all (up to 1000) of the objects in a bucket. You can use the request parameters as selection criteria to return a subset of the objects in a bucket. A 200 OK response can contain valid or invalid XML. Be sure to design your application to parse the contents of the response and handle it appropriately.

```java
CompletableFuture<ListBucketResult1> objectsV1Async(
    final String delimiter,
    final String encodingType,
    final String marker,
    final String maxKeys,
    final String prefix,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `delimiter` | `String` | Query, Required | - |
| `encodingType` | `String` | Query, Required | - |
| `marker` | `String` | Query, Required | - |
| `maxKeys` | `String` | Query, Required | - |
| `prefix` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

[`ListBucketResult1`](../../doc/models/list-bucket-result-1.md)

## Example Usage

```java
String delimiter = "{{Delimiter}}";
String encodingType = "{{EncodingType}}";
String marker = "{{Marker}}";
String maxKeys = "{{MaxKeys}}";
String prefix = "{{Prefix}}";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

objectsController.objectsV1Async(delimiter, encodingType, marker, maxKeys, prefix, xAmzContentSha256, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response *(as XML)*

```xml
<ListBucketResult>
  <Name>working-demo-2</Name>
  <Prefix></Prefix>
  <Marker></Marker>
  <MaxKeys>1000</MaxKeys>
  <IsTruncated>false</IsTruncated>
  <Contents>
    <Key>another-folder/</Key>
    <LastModified>2019-11-17T05:08:53Z</LastModified>
    <ETag>"d41d8cd98f00b204e9800998ecf8427e"</ETag>
    <Size>0</Size>
    <Owner>
      <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
      <DisplayName>kinlane</DisplayName>
    </Owner>
    <StorageClass>STANDARD</StorageClass>
  </Contents>
  <Contents>
    <Key>bf-skinner.jpg</Key>
    <LastModified>2019-11-17T05:09:04Z</LastModified>
    <ETag>"a8478262b03109b46277979cad682155"</ETag>
    <Size>47000</Size>
    <Owner>
      <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
      <DisplayName>kinlane</DisplayName>
    </Owner>
    <StorageClass>STANDARD</StorageClass>
  </Contents>
  <Contents>
    <Key>test123/</Key>
    <LastModified>2019-11-17T05:08:47Z</LastModified>
    <ETag>"d41d8cd98f00b204e9800998ecf8427e"</ETag>
    <Size>0</Size>
    <Owner>
      <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
      <DisplayName>kinlane</DisplayName>
    </Owner>
    <StorageClass>STANDARD</StorageClass>
  </Contents>
  <Contents>
    <Key>test123/api-with-examples.yaml.txt</Key>
    <LastModified>2019-11-17T06:30:15Z</LastModified>
    <ETag>"c49414d54deb9ce2e61488424adfaaa2"</ETag>
    <Size>6337</Size>
    <Owner>
      <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
      <DisplayName>kinlane</DisplayName>
    </Owner>
    <StorageClass>STANDARD</StorageClass>
  </Contents>
  <Contents>
    <Key>test123/callback-example.yaml.txt</Key>
    <LastModified>2019-11-17T06:30:15Z</LastModified>
    <ETag>"ee22b187e786232f2d01f943e8410b81"</ETag>
    <Size>2158</Size>
    <Owner>
      <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
      <DisplayName>kinlane</DisplayName>
    </Owner>
    <StorageClass>STANDARD</StorageClass>
  </Contents>
</ListBucketResult>
```


# Objects V2

Returns some or all (up to 1000) of the objects in a bucket. You can use the request parameters as selection criteria to return a subset of the objects in a bucket. A 200 OK response can contain valid or invalid XML. Be sure to design your application to parse the contents of the response and handle it appropriately.

```java
CompletableFuture<Void> objectsV2Async(
    final int listType,
    final String continuationToken,
    final String delimiter,
    final String encodingType,
    final String fetchOwner,
    final String maxKeys,
    final String prefix,
    final String startAfter,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `listType` | `int` | Query, Required | - |
| `continuationToken` | `String` | Query, Required | - |
| `delimiter` | `String` | Query, Required | - |
| `encodingType` | `String` | Query, Required | - |
| `fetchOwner` | `String` | Query, Required | - |
| `maxKeys` | `String` | Query, Required | - |
| `prefix` | `String` | Query, Required | - |
| `startAfter` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
int listType = 2;
String continuationToken = "{{ContinuationToken}}";
String delimiter = "{{Delimiter}}";
String encodingType = "{{EncodingType}}";
String fetchOwner = "{{FetchOwner}}";
String maxKeys = "{{MaxKeys}}";
String prefix = "{{Prefix}}";
String startAfter = "{{StartAfter}}";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

objectsController.objectsV2Async(listType, continuationToken, delimiter, encodingType, fetchOwner, maxKeys, prefix, startAfter, xAmzContentSha256, bucket).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Object 1

Retrieves objects from Amazon S3. To use GET, you must have READ access to the object. If you grant READ access to the anonymous user, you can return the object without using an authorization header.

```java
CompletableFuture<Void> object1Async(
    final String xAmzContentSha256,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";
String key = "key0";

objectsController.object1Async(xAmzContentSha256, bucket, key).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Parts

Lists the parts that have been uploaded for a specific multipart upload. This operation must include the upload ID, which you obtain by sending the initiate multipart upload request (see CreateMultipartUpload). This request returns a maximum of 1,000 uploaded parts. The default number of parts returned is 1,000 parts. You can restrict the number of parts returned by specifying the max-parts request parameter. If your multipart upload consists of more than 1,000 parts, the response returns an IsTruncated field with the value of true, and a NextPartNumberMarker element. In subsequent ListParts requests you can include the part-number-marker query string parameter and set its value to the NextPartNumberMarker field value from the previous response.

```java
CompletableFuture<Void> partsAsync(
    final String maxParts,
    final String partNumberMarker,
    final String uploadId,
    final String xAmzContentSha256,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `maxParts` | `String` | Query, Required | - |
| `partNumberMarker` | `String` | Query, Required | - |
| `uploadId` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String maxParts = "{{MaxParts}}";
String partNumberMarker = "{{PartNumberMarker}}";
String uploadId = "{{UploadId}}";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";
String key = "key0";

objectsController.partsAsync(maxParts, partNumberMarker, uploadId, xAmzContentSha256, bucket, key).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Copy Object

Creates a copy of an object that is already stored in Amazon S3.

```java
CompletableFuture<DynamicResponse> copyObjectAsync(
    final String xAmzContentSha256,
    final String body,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String body = "hello";
String bucket = "bucket2";
String key = "key0";

objectsController.copyObjectAsync(xAmzContentSha256, body, bucket, key).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Delete Object

Removes the null version (if there is one) of an object and inserts a delete marker, which becomes the latest version of the object. If there isn't a null version, Amazon S3 does not remove any objects.

```java
CompletableFuture<Void> deleteObjectAsync(
    final String versionId,
    final String xAmzContentSha256,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `versionId` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String versionId = "VersionId";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";
String key = "key0";

objectsController.deleteObjectAsync(versionId, xAmzContentSha256, bucket, key).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Delete Objects

This operation enables you to delete multiple objects from a bucket using a single HTTP request. If you know the object keys that you want to delete, then this operation provides a suitable alternative to sending individual delete requests, reducing per-request overhead.

```java
CompletableFuture<Void> deleteObjectsAsync(
    final String delete,
    final String xAmzContentSha256,
    final String body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `delete` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String delete = "delete6";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<Delete xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n   <Object>\n      <Key>string</Key>\n      <VersionId>string</VersionId>\n   </Object>\n   ...\n   <Quiet>boolean</Quiet>\n</Delete>";
String bucket = "bucket2";

objectsController.deleteObjectsAsync(delete, xAmzContentSha256, body, bucket).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

