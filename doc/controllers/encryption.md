# Encryption

```ts
const encryptionController = new EncryptionController(client);
```

## Class Name

`EncryptionController`

## Methods

* [Bucket Encryption](../../doc/controllers/encryption.md#bucket-encryption)
* [Bucket Encryption 1](../../doc/controllers/encryption.md#bucket-encryption-1)
* [Delete Bucket Encryption](../../doc/controllers/encryption.md#delete-bucket-encryption)


# Bucket Encryption

Returns the default encryption configuration for an Amazon S3 bucket. For information about the Amazon S3 default encryption feature, see Amazon S3 Default Bucket Encryption.

```ts
async bucketEncryption(
  encryption: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `encryption` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const encryption = 'encryption4';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await encryptionController.bucketEncryption(
    encryption,
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
"<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<ServerSideEncryptionConfiguration xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><Rule><ApplyServerSideEncryptionByDefault><SSEAlgorithm>AES256</SSEAlgorithm></ApplyServerSideEncryptionByDefault></Rule></ServerSideEncryptionConfiguration>"
```


# Bucket Encryption 1

This implementation of the PUT operation uses the encryption subresource to set the default encryption state of an existing bucket.

```ts
async bucketEncryption1(
  encryption: string,
  body: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `encryption` | `string` | Query, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const encryption = 'encryption4';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<ServerSideEncryptionConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <Rule><ApplyServerSideEncryptionByDefault><SSEAlgorithm>AES256</SSEAlgorithm></ApplyServerSideEncryptionByDefault></Rule>\n</ServerSideEncryptionConfiguration>';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await encryptionController.bucketEncryption1(
    encryption,
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


# Delete Bucket Encryption

This implementation of the DELETE operation removes default encryption from the bucket.

```ts
async deleteBucketEncryption(
  encryption: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `encryption` | `string` | Query, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const encryption = 'encryption4';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await encryptionController.deleteBucketEncryption(
    encryption,
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

