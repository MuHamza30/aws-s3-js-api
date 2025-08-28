# Buckets

```ts
const bucketsController = new BucketsController(client);
```

## Class Name

`BucketsController`

## Methods

* [Head](../../doc/controllers/buckets.md#head)
* [List](../../doc/controllers/buckets.md#list)
* [Create](../../doc/controllers/buckets.md#create)
* [Delete](../../doc/controllers/buckets.md#delete)


# Head

```ts
async head(
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await bucketsController.head(bucket);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```


# List

Returns a list of all buckets owned by the authenticated sender of the request.

```ts
async list(
  requestOptions?: RequestOptions
): Promise<ApiResponse<ListAllMyBucketsResult>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ListAllMyBucketsResult`](../../doc/models/list-all-my-buckets-result.md).

## Example Usage

```ts
try {
  const { result, ...httpResponse } = await bucketsController.list();
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

```ts
async create(
  body: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const body = '<?xml version="1.0" encoding="UTF-8"?>\n<CreateBucketConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <LocationConstraint>us-west-1</LocationConstraint>\n</CreateBucketConfiguration>';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await bucketsController.create(
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


# Delete

Deletes the bucket. All objects (including all object versions and Delete Markers) in the bucket must be deleted before the bucket itself can be deleted.

```ts
async mDelete(
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const bucket = 'my-bucket-storage-2';

try {
  const { result, ...httpResponse } = await bucketsController.mDelete(bucket);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

