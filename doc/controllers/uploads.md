# Uploads

```ts
const uploadsController = new UploadsController(client);
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

```ts
async createMultipart(
  uploads: string,
  xAmzContentSha256: string,
  file: FileWrapper,
  bucket: string,
  key: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uploads` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `file` | `FileWrapper` | Form, Required | - |
| `bucket` | `string` | Template, Required | - |
| `key` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const uploads = 'uploads2';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const file = new FileWrapper(fs.createReadStream('dummy_file'));

const bucket = 'bucket2';

const key = 'key0';

try {
  const { result, ...httpResponse } = await uploadsController.createMultipart(
    uploads,
    xAmzContentSha256,
    file,
    bucket,
    key
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


# Multipart

This operation lists in-progress multipart uploads. An in-progress multipart upload is a multipart upload that has been initiated using the Initiate Multipart Upload request, but has not yet been completed or aborted.

```ts
async multipart(
  uploads: string,
  delimiter: string,
  encodingType: string,
  keyMarker: string,
  maxUploads: string,
  prefix: string,
  uploadIdMarker: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ListMultipartUploadsResult>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uploads` | `string` | Query, Required | - |
| `delimiter` | `string` | Query, Required | - |
| `encodingType` | `string` | Query, Required | - |
| `keyMarker` | `string` | Query, Required | - |
| `maxUploads` | `string` | Query, Required | - |
| `prefix` | `string` | Query, Required | - |
| `uploadIdMarker` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ListMultipartUploadsResult`](../../doc/models/list-multipart-uploads-result.md).

## Example Usage

```ts
const uploads = 'uploads2';

const delimiter = '{{Delimiter}}';

const encodingType = '{{EncodingType}}';

const keyMarker = '{{KeyMarker}}';

const maxUploads = '{{MaxUploads}}';

const prefix = '{{Prefix}}';

const uploadIdMarker = '{{UploadIdMarker}}';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await uploadsController.multipart(
    uploads,
    delimiter,
    encodingType,
    keyMarker,
    maxUploads,
    prefix,
    uploadIdMarker,
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

```ts
async completeMultipart(
  uploadId: string,
  xAmzContentSha256: string,
  body: string,
  bucket: string,
  key: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uploadId` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `key` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const uploadId = 'UploadId';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<CompleteMultipartUpload xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <Part>\n      <ETag>string</ETag>\n      <PartNumber>integer</PartNumber>\n   </Part>\n</CompleteMultipartUpload>';

const bucket = 'bucket2';

const key = 'key0';

try {
  const { result, ...httpResponse } = await uploadsController.completeMultipart(
    uploadId,
    xAmzContentSha256,
    body,
    bucket,
    key
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


# Part

Completes a multipart upload by assembling previously uploaded parts.

```ts
async part(
  uploadId: string,
  xAmzContentSha256: string,
  body: string,
  bucket: string,
  key: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uploadId` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `key` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const uploadId = '{{uploadId}}';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<CompleteMultipartUpload xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <Part>\n      <ETag>string</ETag>\n      <PartNumber>integer</PartNumber>\n   </Part>\n</CompleteMultipartUpload>';

const bucket = 'bucket2';

const key = 'key0';

try {
  const { result, ...httpResponse } = await uploadsController.part(
    uploadId,
    xAmzContentSha256,
    body,
    bucket,
    key
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


# Part Copy

Completes a multipart upload by assembling previously uploaded parts.

```ts
async partCopy(
  uploadId: string,
  partNumber: string,
  xAmzContentSha256: string,
  body: string,
  bucket: string,
  key: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uploadId` | `string` | Query, Required | - |
| `partNumber` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `key` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const uploadId = '{{uploadId}}';

const partNumber = '{{PartNumber}}';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<CompleteMultipartUpload xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <Part>\n      <ETag>string</ETag>\n      <PartNumber>integer</PartNumber>\n   </Part>\n</CompleteMultipartUpload>';

const bucket = 'bucket2';

const key = 'key0';

try {
  const { result, ...httpResponse } = await uploadsController.partCopy(
    uploadId,
    partNumber,
    xAmzContentSha256,
    body,
    bucket,
    key
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


# Abort Multipart

Completes a multipart upload by assembling previously uploaded parts.

```ts
async abortMultipart(
  uploadId: string,
  xAmzContentSha256: string,
  body: string,
  bucket: string,
  key: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uploadId` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `key` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const uploadId = '{{uploadId}}';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<CompleteMultipartUpload xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <Part>\n      <ETag>string</ETag>\n      <PartNumber>integer</PartNumber>\n   </Part>\n</CompleteMultipartUpload>';

const bucket = 'bucket2';

const key = 'key0';

try {
  const { result, ...httpResponse } = await uploadsController.abortMultipart(
    uploadId,
    xAmzContentSha256,
    body,
    bucket,
    key
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

