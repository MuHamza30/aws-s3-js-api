# Public Access Block

```ts
const publicAccessBlockController = new PublicAccessBlockController(client);
```

## Class Name

`PublicAccessBlockController`

## Methods

* [Public Access Block](../../doc/controllers/public-access-block.md#public-access-block)
* [Public Access Block 1](../../doc/controllers/public-access-block.md#public-access-block-1)
* [Public Access Block 2](../../doc/controllers/public-access-block.md#public-access-block-2)


# Public Access Block

Retrieves the PublicAccessBlock configuration for an Amazon S3 bucket. In order to use this operation, you must have the s3:GetBucketPublicAccessBlock permission. For more information about Amazon S3 permissions, see Specifying Permissions in a Policy.

```ts
async publicAccessBlock(
  publicAccessBlock: string,
  xAmzContentSha256: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `publicAccessBlock` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const publicAccessBlock = 'publicAccessBlock0';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

try {
  const { result, ...httpResponse } = await publicAccessBlockController.publicAccessBlock(
    publicAccessBlock,
    xAmzContentSha256
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


# Public Access Block 1

Retrieves the PublicAccessBlock configuration for an Amazon S3 bucket. In order to use this operation, you must have the s3:GetBucketPublicAccessBlock permission. For more information about Amazon S3 permissions, see Specifying Permissions in a Policy.

```ts
async publicAccessBlock1(
  publicAccessBlock: string,
  xAmzContentSha256: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `publicAccessBlock` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const publicAccessBlock = 'publicAccessBlock0';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

try {
  const { result, ...httpResponse } = await publicAccessBlockController.publicAccessBlock1(
    publicAccessBlock,
    xAmzContentSha256
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


# Public Access Block 2

Removes the PublicAccessBlock configuration for an Amazon S3 bucket. In order to use this operation, you must have the s3:PutBucketPublicAccessBlock permission.

```ts
async publicAccessBlock2(
  publicAccessBlock: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `publicAccessBlock` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const publicAccessBlock = 'publicAccessBlock0';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await publicAccessBlockController.publicAccessBlock2(
    publicAccessBlock,
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

