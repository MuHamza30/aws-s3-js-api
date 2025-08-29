# Replication

```java
ReplicationController replicationController = client.getReplicationController();
```

## Class Name

`ReplicationController`

## Methods

* [Bucket Replication](../../doc/controllers/replication.md#bucket-replication)
* [Bucket Replication 1](../../doc/controllers/replication.md#bucket-replication-1)
* [Delete Bucket Replication](../../doc/controllers/replication.md#delete-bucket-replication)


# Bucket Replication

Returns the replication configuration of a bucket.

```java
CompletableFuture<Void> bucketReplicationAsync(
    final String replication,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `replication` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String replication = "replication0";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

replicationController.bucketReplicationAsync(replication, xAmzContentSha256, bucket).thenAccept(result -> {
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
| 404 | Not Found | [`ErrorException`](../../doc/models/error-exception.md) |


# Bucket Replication 1

Creates a replication configuration or replaces an existing one.

```java
CompletableFuture<Void> bucketReplication1Async(
    final String replication,
    final String contentMD5,
    final String xAmzBucketObjectLockToken,
    final String body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `replication` | `String` | Query, Required | - |
| `contentMD5` | `String` | Header, Required | - |
| `xAmzBucketObjectLockToken` | `String` | Header, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String replication = "replication0";
String contentMD5 = "{{contentMD5}}";
String xAmzBucketObjectLockToken = "Token";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<ReplicationConfiguration xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n   <Role>string</Role>\n   <Rule>\n      <DeleteMarkerReplication>\n         <Status>string</Status>\n      </DeleteMarkerReplication>\n      <Destination>\n         <AccessControlTranslation>\n            <Owner>string</Owner>\n         </AccessControlTranslation>\n         <Account>string</Account>\n         <Bucket>string</Bucket>\n         <EncryptionConfiguration>\n            <ReplicaKmsKeyID>string</ReplicaKmsKeyID>\n         </EncryptionConfiguration>\n         <Metrics>\n            <EventThreshold>\n               <Hours>integer</Hours>\n               <Minutes>integer</Minutes>\n            </EventThreshold>\n            <Status>string</Status>\n         </Metrics>\n         <ReplicationTime>\n            <Status>string</Status>\n            <Time>\n               <Hours>integer</Hours>\n               <Minutes>integer</Minutes>\n            </Time>\n         </ReplicationTime>\n         <StorageClass>string</StorageClass>\n      </Destination>\n      <ExistingObjectReplication>\n         <Status>string</Status>\n      </ExistingObjectReplication>\n      <Filter>\n         <And>\n            <Prefix>string</Prefix>\n            <Tag>\n               <Key>string</Key>\n               <Value>string</Value>\n            </Tag>\n         </And>\n         <Prefix>string</Prefix>\n         <Tag>\n            <Key>string</Key>\n            <Value>string</Value>\n         </Tag>\n      </Filter>\n      <ID>string</ID>\n      <Prefix>string</Prefix>\n      <Priority>integer</Priority>\n      <SourceSelectionCriteria>\n         <SseKmsEncryptedObjects>\n            <Status>string</Status>\n         </SseKmsEncryptedObjects>\n      </SourceSelectionCriteria>\n      <Status>string</Status>\n   </Rule>\n</ReplicationConfiguration>";
String bucket = "bucket2";

replicationController.bucketReplication1Async(replication, contentMD5, xAmzBucketObjectLockToken, body, bucket).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Delete Bucket Replication

Deletes the replication configuration from the bucket.

```java
CompletableFuture<DynamicResponse> deleteBucketReplicationAsync(
    final String replication,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `replication` | `String` | Query, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String replication = "replication0";
String bucket = "bucket2";

replicationController.deleteBucketReplicationAsync(replication, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

