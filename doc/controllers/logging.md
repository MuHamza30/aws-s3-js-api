# Logging

```ts
const loggingController = new LoggingController(client);
```

## Class Name

`LoggingController`

## Methods

* [Bucket Logging](../../doc/controllers/logging.md#bucket-logging)
* [Bucket Logging 1](../../doc/controllers/logging.md#bucket-logging-1)


# Bucket Logging

Returns the logging status of a bucket and the permissions users have to view and modify that status. To use GET, you must be the bucket owner.

```ts
async bucketLogging(
  logging: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `logging` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const logging = 'logging0';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await loggingController.bucketLogging(
    logging,
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


# Bucket Logging 1

Set the logging parameters for a bucket and to specify permissions for who can view and modify the logging parameters. All logs are saved to buckets in the same AWS Region as the source bucket. To set the logging status of a bucket, you must be the bucket owner.

```ts
async bucketLogging1(
  logging: string,
  contentMD5: string,
  body: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `logging` | `string` | Query, Required | - |
| `contentMD5` | `string` | Header, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const logging = 'logging0';

const contentMD5 = '{{contentMD5}}';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<BucketLoggingStatus xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <LoggingEnabled>\n      <TargetBucket>working-demo-2</TargetBucket>\n   </LoggingEnabled>\n</BucketLoggingStatus>';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await loggingController.bucketLogging1(
    logging,
    contentMD5,
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

