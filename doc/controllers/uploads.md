# Uploads

```java
UploadsController uploadsController = client.getUploadsController();
```

## Class Name

`UploadsController`

## Methods

* [Create Multipart](../../doc/controllers/uploads.md#create-multipart)
* [Multipart](../../doc/controllers/uploads.md#multipart)
* [Complete Multipart](../../doc/controllers/uploads.md#complete-multipart)
* [Part](../../doc/controllers/uploads.md#part)
* [Part Copy](../../doc/controllers/uploads.md#part-copy)
* [Abort Multipart](../../doc/controllers/uploads.md#abort-multipart)


# Create Multipart

This operation initiates a multipart upload and returns an upload ID. This upload ID is used to associate all of the parts in the specific multipart upload. You specify this upload ID in each of your subsequent upload part requests (see UploadPart). You also include this upload ID in the final request to either complete or abort the multipart upload request.

```java
CompletableFuture<Void> createMultipartAsync(
    final String uploads,
    final String xAmzContentSha256,
    final FileWrapper file,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uploads` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `file` | `FileWrapper` | Form, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String uploads = "uploads2";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
FileWrapper file = new FileWrapper(new File("dummy_file"), "optional-content-type");
String bucket = "bucket2";
String key = "key0";

uploadsController.createMultipartAsync(uploads, xAmzContentSha256, file, bucket, key).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Multipart

This operation lists in-progress multipart uploads. An in-progress multipart upload is a multipart upload that has been initiated using the Initiate Multipart Upload request, but has not yet been completed or aborted.

```java
CompletableFuture<ListMultipartUploadsResult> multipartAsync(
    final String uploads,
    final String delimiter,
    final String encodingType,
    final String keyMarker,
    final String maxUploads,
    final String prefix,
    final String uploadIdMarker,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uploads` | `String` | Query, Required | - |
| `delimiter` | `String` | Query, Required | - |
| `encodingType` | `String` | Query, Required | - |
| `keyMarker` | `String` | Query, Required | - |
| `maxUploads` | `String` | Query, Required | - |
| `prefix` | `String` | Query, Required | - |
| `uploadIdMarker` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

[`ListMultipartUploadsResult`](../../doc/models/list-multipart-uploads-result.md)

## Example Usage

```java
String uploads = "uploads2";
String delimiter = "{{Delimiter}}";
String encodingType = "{{EncodingType}}";
String keyMarker = "{{KeyMarker}}";
String maxUploads = "{{MaxUploads}}";
String prefix = "{{Prefix}}";
String uploadIdMarker = "{{UploadIdMarker}}";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

uploadsController.multipartAsync(uploads, delimiter, encodingType, keyMarker, maxUploads, prefix, uploadIdMarker, xAmzContentSha256, bucket).thenAccept(result -> {
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
<ListMultipartUploadsResult>
  <Bucket>working-demo-2</Bucket>
  <KeyMarker></KeyMarker>
  <UploadIdMarker></UploadIdMarker>
  <NextKeyMarker></NextKeyMarker>
  <NextUploadIdMarker></NextUploadIdMarker>
  <MaxUploads>1000</MaxUploads>
  <IsTruncated>false</IsTruncated>
</ListMultipartUploadsResult>
```


# Complete Multipart

Completes a multipart upload by assembling previously uploaded parts.

```java
CompletableFuture<Void> completeMultipartAsync(
    final String uploadId,
    final String xAmzContentSha256,
    final String body,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uploadId` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String uploadId = "UploadId";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<CompleteMultipartUpload xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n   <Part>\n      <ETag>string</ETag>\n      <PartNumber>integer</PartNumber>\n   </Part>\n</CompleteMultipartUpload>";
String bucket = "bucket2";
String key = "key0";

uploadsController.completeMultipartAsync(uploadId, xAmzContentSha256, body, bucket, key).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Part

Completes a multipart upload by assembling previously uploaded parts.

```java
CompletableFuture<Void> partAsync(
    final String uploadId,
    final String xAmzContentSha256,
    final String body,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uploadId` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String uploadId = "{{uploadId}}";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<CompleteMultipartUpload xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n   <Part>\n      <ETag>string</ETag>\n      <PartNumber>integer</PartNumber>\n   </Part>\n</CompleteMultipartUpload>";
String bucket = "bucket2";
String key = "key0";

uploadsController.partAsync(uploadId, xAmzContentSha256, body, bucket, key).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Part Copy

Completes a multipart upload by assembling previously uploaded parts.

```java
CompletableFuture<Void> partCopyAsync(
    final String uploadId,
    final String partNumber,
    final String xAmzContentSha256,
    final String body,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uploadId` | `String` | Query, Required | - |
| `partNumber` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String uploadId = "{{uploadId}}";
String partNumber = "{{PartNumber}}";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<CompleteMultipartUpload xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n   <Part>\n      <ETag>string</ETag>\n      <PartNumber>integer</PartNumber>\n   </Part>\n</CompleteMultipartUpload>";
String bucket = "bucket2";
String key = "key0";

uploadsController.partCopyAsync(uploadId, partNumber, xAmzContentSha256, body, bucket, key).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Abort Multipart

Completes a multipart upload by assembling previously uploaded parts.

```java
CompletableFuture<Void> abortMultipartAsync(
    final String uploadId,
    final String xAmzContentSha256,
    final String body,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uploadId` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String uploadId = "{{uploadId}}";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<CompleteMultipartUpload xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n   <Part>\n      <ETag>string</ETag>\n      <PartNumber>integer</PartNumber>\n   </Part>\n</CompleteMultipartUpload>";
String bucket = "bucket2";
String key = "key0";

uploadsController.abortMultipartAsync(uploadId, xAmzContentSha256, body, bucket, key).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

