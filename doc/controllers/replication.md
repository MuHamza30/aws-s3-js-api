# Replication

```ts
const replicationController = new ReplicationController(client);
```

## Class Name

`ReplicationController`

## Methods

* [Bucket Replication](../../doc/controllers/replication.md#bucket-replication)
* [Bucket Replication 1](../../doc/controllers/replication.md#bucket-replication-1)
* [Delete Bucket Replication](../../doc/controllers/replication.md#delete-bucket-replication)


# Bucket Replication

Returns the replication configuration of a bucket.

```ts
async bucketReplication(
  replication: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `replication` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const replication = 'replication0';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await replicationController.bucketReplication(
    replication,
    xAmzContentSha256,
    bucket
  );
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | Not Found | [`CustomError`](../../doc/models/custom-error.md) |


# Bucket Replication 1

Creates a replication configuration or replaces an existing one.

```ts
async bucketReplication1(
  replication: string,
  contentMD5: string,
  xAmzBucketObjectLockToken: string,
  body: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `replication` | `string` | Query, Required | - |
| `contentMD5` | `string` | Header, Required | - |
| `xAmzBucketObjectLockToken` | `string` | Header, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const replication = 'replication0';

const contentMD5 = '{{contentMD5}}';

const xAmzBucketObjectLockToken = 'Token';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<ReplicationConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <Role>string</Role>\n   <Rule>\n      <DeleteMarkerReplication>\n         <Status>string</Status>\n      </DeleteMarkerReplication>\n      <Destination>\n         <AccessControlTranslation>\n            <Owner>string</Owner>\n         </AccessControlTranslation>\n         <Account>string</Account>\n         <Bucket>string</Bucket>\n         <EncryptionConfiguration>\n            <ReplicaKmsKeyID>string</ReplicaKmsKeyID>\n         </EncryptionConfiguration>\n         <Metrics>\n            <EventThreshold>\n               <Hours>integer</Hours>\n               <Minutes>integer</Minutes>\n            </EventThreshold>\n            <Status>string</Status>\n         </Metrics>\n         <ReplicationTime>\n            <Status>string</Status>\n            <Time>\n               <Hours>integer</Hours>\n               <Minutes>integer</Minutes>\n            </Time>\n         </ReplicationTime>\n         <StorageClass>string</StorageClass>\n      </Destination>\n      <ExistingObjectReplication>\n         <Status>string</Status>\n      </ExistingObjectReplication>\n      <Filter>\n         <And>\n            <Prefix>string</Prefix>\n            <Tag>\n               <Key>string</Key>\n               <Value>string</Value>\n            </Tag>\n         </And>\n         <Prefix>string</Prefix>\n         <Tag>\n            <Key>string</Key>\n            <Value>string</Value>\n         </Tag>\n      </Filter>\n      <ID>string</ID>\n      <Prefix>string</Prefix>\n      <Priority>integer</Priority>\n      <SourceSelectionCriteria>\n         <SseKmsEncryptedObjects>\n            <Status>string</Status>\n         </SseKmsEncryptedObjects>\n      </SourceSelectionCriteria>\n      <Status>string</Status>\n   </Rule>\n</ReplicationConfiguration>';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await replicationController.bucketReplication1(
    replication,
    contentMD5,
    xAmzBucketObjectLockToken,
    body,
    bucket
  );
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```


# Delete Bucket Replication

Deletes the replication configuration from the bucket.

```ts
async deleteBucketReplication(
  replication: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `replication` | `string` | Query, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const replication = 'replication0';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await replicationController.deleteBucketReplication(
    replication,
    bucket
  );
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

