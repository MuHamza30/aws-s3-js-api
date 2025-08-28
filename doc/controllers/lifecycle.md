# Lifecycle

```ts
const lifecycleController = new LifecycleController(client);
```

## Class Name

`LifecycleController`

## Methods

* [Bucket Lifecycle](../../doc/controllers/lifecycle.md#bucket-lifecycle)
* [Delete Bucket Lifecycle](../../doc/controllers/lifecycle.md#delete-bucket-lifecycle)
* [Bucket Lifecycle 1](../../doc/controllers/lifecycle.md#bucket-lifecycle-1)


# Bucket Lifecycle

Returns the lifecycle configuration information set on the bucket. For information about lifecycle configuration, see Object Lifecycle Management.

```ts
async bucketLifecycle(
  lifecycle: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `lifecycle` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const lifecycle = 'lifecycle8';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await lifecycleController.bucketLifecycle(
    lifecycle,
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

## Example Response

```
"<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<LifecycleConfiguration xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><Rule><ID>/my</ID><Filter><Tag><Key>test</Key><Value></Value></Tag></Filter><Status>Enabled</Status><Expiration><Days>365</Days></Expiration></Rule></LifecycleConfiguration>"
```


# Delete Bucket Lifecycle

Deletes the lifecycle configuration from the specified bucket. Amazon S3 removes all the lifecycle configuration rules in the lifecycle subresource associated with the bucket. Your objects never expire, and Amazon S3 no longer automatically deletes any objects on the basis of rules contained in the deleted lifecycle configuration.

```ts
async deleteBucketLifecycle(
  lifecycle: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `lifecycle` | `string` | Query, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const lifecycle = 'lifecycle8';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await lifecycleController.deleteBucketLifecycle(
    lifecycle,
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


# Bucket Lifecycle 1

Creates a new lifecycle configuration for the bucket or replaces an existing lifecycle configuration.

```ts
async bucketLifecycle1(
  lifecycle: string,
  contentMD5: string,
  body: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `lifecycle` | `string` | Query, Required | - |
| `contentMD5` | `string` | Header, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const lifecycle = 'lifecycle8';

const contentMD5 = '{{contentMD5}}';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<LifecycleConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/"><Rule><ID>/my</ID><Filter><Tag><Key>test</Key><Value></Value></Tag></Filter><Status>Enabled</Status><Expiration><Days>365</Days></Expiration></Rule></LifecycleConfiguration>';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await lifecycleController.bucketLifecycle1(
    lifecycle,
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

