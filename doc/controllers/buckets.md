# Buckets

```java
BucketsController bucketsController = client.getBucketsController();
```

## Class Name

`BucketsController`

## Methods

* [Head](../../doc/controllers/buckets.md#head)
* [List](../../doc/controllers/buckets.md#list)
* [Create](../../doc/controllers/buckets.md#create)
* [Delete](../../doc/controllers/buckets.md#delete)


# Head

```java
CompletableFuture<DynamicResponse> headAsync(
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String bucket = "bucket2";

bucketsController.headAsync(bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# List

Returns a list of all buckets owned by the authenticated sender of the request.

```java
CompletableFuture<ListAllMyBucketsResult> listAsync()
```

## Response Type

[`ListAllMyBucketsResult`](../../doc/models/list-all-my-buckets-result.md)

## Example Usage

```java
bucketsController.listAsync().thenAccept(result -> {
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
<ListAllMyBucketsResult>
  <Owner>
    <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
    <DisplayName>kinlane</DisplayName>
  </Owner>
  <Buckets>
    <Bucket>
      <Name>working-demo-2</Name>
      <CreationDate>2019-11-17T04:45:13Z</CreationDate>
    </Bucket>
  </Buckets>
</ListAllMyBucketsResult>
```


# Create

Creates a new bucket. To create a bucket, you must register with Amazon S3 and have a valid AWS Access Key ID to authenticate requests. Anonymous requests are never allowed to create buckets. By creating the bucket, you become the bucket owner.

```java
CompletableFuture<DynamicResponse> createAsync(
    final String body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<CreateBucketConfiguration xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n   <LocationConstraint>us-west-1</LocationConstraint>\n</CreateBucketConfiguration>";
String bucket = "bucket2";

bucketsController.createAsync(body, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Delete

Deletes the bucket. All objects (including all object versions and Delete Markers) in the bucket must be deleted before the bucket itself can be deleted.

```java
CompletableFuture<Void> deleteAsync(
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String bucket = "my-bucket-storage-2";

bucketsController.deleteAsync(bucket).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

