# Accelerate

```ts
const accelerateController = new AccelerateController(client);
```

## Class Name

`AccelerateController`

## Methods

* [Bucket Accelerate Configuration](../../doc/controllers/accelerate.md#bucket-accelerate-configuration)
* [Bucket Accelerate Configuration 1](../../doc/controllers/accelerate.md#bucket-accelerate-configuration-1)
* [Get Bucket Accelerate Configuration](../../doc/controllers/accelerate.md#get-bucket-accelerate-configuration)


# Bucket Accelerate Configuration

Sets the accelerate configuration of an existing bucket. Amazon S3 Transfer Acceleration is a bucket-level feature that enables you to perform faster data transfers to Amazon S3.

```ts
async bucketAccelerateConfiguration(
  accelerate: string,
  body: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accelerate` | `string` | Query, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const accelerate = 'accelerate6';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<AccelerateConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <Status>Enabled</Status>\n</AccelerateConfiguration>';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await accelerateController.bucketAccelerateConfiguration(
    accelerate,
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


# Bucket Accelerate Configuration 1

Sets the accelerate configuration of an existing bucket. Amazon S3 Transfer Acceleration is a bucket-level feature that enables you to perform faster data transfers to Amazon S3.

```ts
async bucketAccelerateConfiguration1(
  accelerate: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ListBucketResult>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accelerate` | `string` | Query, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ListBucketResult`](../../doc/models/list-bucket-result.md).

## Example Usage

```ts
const accelerate = 'accelerate6';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await accelerateController.bucketAccelerateConfiguration1(
    accelerate,
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

## Example Response *(as XML)*

```xml
<ListBucketResult>
  <Name>working-demo-2</Name>
  <Prefix></Prefix>
  <Marker></Marker>
  <MaxKeys>1000</MaxKeys>
  <IsTruncated>false</IsTruncated>
</ListBucketResult>
```


# Get Bucket Accelerate Configuration

This implementation of the GET operation uses the accelerate subresource to return the Transfer Acceleration state of a bucket, which is either Enabled or Suspended. Amazon S3 Transfer Acceleration is a bucket-level feature that enables you to perform faster data transfers to and from Amazon S3.

```ts
async getBucketAccelerateConfiguration(
  accelerate: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accelerate` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const accelerate = 'accelerate6';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await accelerateController.getBucketAccelerateConfiguration(
    accelerate,
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

