# Objects

```ts
const objectsController = new ObjectsController(client);
```

## Class Name

`ObjectsController`

## Methods

* [Object](../../doc/controllers/objects.md#object)
* [Objects V1](../../doc/controllers/objects.md#objects-v1)
* [Objects V2](../../doc/controllers/objects.md#objects-v2)
* [Object 1](../../doc/controllers/objects.md#object-1)
* [Parts](../../doc/controllers/objects.md#parts)
* [Copy Object](../../doc/controllers/objects.md#copy-object)
* [Delete Object](../../doc/controllers/objects.md#delete-object)
* [Delete Objects](../../doc/controllers/objects.md#delete-objects)


# Object

The HEAD operation retrieves metadata from an object without returning the object itself. This operation is useful if you're only interested in an object's metadata. To use HEAD, you must have READ access to the object.

```ts
async object(
  partNumber: string,
  versionId: string,
  xAmzContentSha256: string,
  bucket: string,
  key: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `partNumber` | `string` | Query, Required | - |
| `versionId` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `key` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const partNumber = 'PartNumber';

const versionId = 'VersionId';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

const key = 'key0';

try {
  const { result, ...httpResponse } = await objectsController.object(
    partNumber,
    versionId,
    xAmzContentSha256,
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

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiError` |


# Objects V1

Returns some or all (up to 1000) of the objects in a bucket. You can use the request parameters as selection criteria to return a subset of the objects in a bucket. A 200 OK response can contain valid or invalid XML. Be sure to design your application to parse the contents of the response and handle it appropriately.

```ts
async objectsV1(
  delimiter: string,
  encodingType: string,
  marker: string,
  maxKeys: string,
  prefix: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ListBucketResult1>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `delimiter` | `string` | Query, Required | - |
| `encodingType` | `string` | Query, Required | - |
| `marker` | `string` | Query, Required | - |
| `maxKeys` | `string` | Query, Required | - |
| `prefix` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ListBucketResult1`](../../doc/models/list-bucket-result-1.md).

## Example Usage

```ts
const delimiter = '{{Delimiter}}';

const encodingType = '{{EncodingType}}';

const marker = '{{Marker}}';

const maxKeys = '{{MaxKeys}}';

const prefix = '{{Prefix}}';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await objectsController.objectsV1(
    delimiter,
    encodingType,
    marker,
    maxKeys,
    prefix,
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
<ListBucketResult>
  <Name>working-demo-2</Name>
  <Prefix></Prefix>
  <Marker></Marker>
  <MaxKeys>1000</MaxKeys>
  <IsTruncated>false</IsTruncated>
  <Contents>
    <Key>another-folder/</Key>
    <LastModified>2019-11-17T05:08:53Z</LastModified>
    <ETag>"d41d8cd98f00b204e9800998ecf8427e"</ETag>
    <Size>0</Size>
    <Owner>
      <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
      <DisplayName>kinlane</DisplayName>
    </Owner>
    <StorageClass>STANDARD</StorageClass>
  </Contents>
  <Contents>
    <Key>bf-skinner.jpg</Key>
    <LastModified>2019-11-17T05:09:04Z</LastModified>
    <ETag>"a8478262b03109b46277979cad682155"</ETag>
    <Size>47000</Size>
    <Owner>
      <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
      <DisplayName>kinlane</DisplayName>
    </Owner>
    <StorageClass>STANDARD</StorageClass>
  </Contents>
  <Contents>
    <Key>test123/</Key>
    <LastModified>2019-11-17T05:08:47Z</LastModified>
    <ETag>"d41d8cd98f00b204e9800998ecf8427e"</ETag>
    <Size>0</Size>
    <Owner>
      <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
      <DisplayName>kinlane</DisplayName>
    </Owner>
    <StorageClass>STANDARD</StorageClass>
  </Contents>
  <Contents>
    <Key>test123/api-with-examples.yaml.txt</Key>
    <LastModified>2019-11-17T06:30:15Z</LastModified>
    <ETag>"c49414d54deb9ce2e61488424adfaaa2"</ETag>
    <Size>6337</Size>
    <Owner>
      <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
      <DisplayName>kinlane</DisplayName>
    </Owner>
    <StorageClass>STANDARD</StorageClass>
  </Contents>
  <Contents>
    <Key>test123/callback-example.yaml.txt</Key>
    <LastModified>2019-11-17T06:30:15Z</LastModified>
    <ETag>"ee22b187e786232f2d01f943e8410b81"</ETag>
    <Size>2158</Size>
    <Owner>
      <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
      <DisplayName>kinlane</DisplayName>
    </Owner>
    <StorageClass>STANDARD</StorageClass>
  </Contents>
</ListBucketResult>
```


# Objects V2

Returns some or all (up to 1000) of the objects in a bucket. You can use the request parameters as selection criteria to return a subset of the objects in a bucket. A 200 OK response can contain valid or invalid XML. Be sure to design your application to parse the contents of the response and handle it appropriately.

```ts
async objectsV2(
  listType: number,
  continuationToken: string,
  delimiter: string,
  encodingType: string,
  fetchOwner: string,
  maxKeys: string,
  prefix: string,
  startAfter: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `listType` | `number` | Query, Required | - |
| `continuationToken` | `string` | Query, Required | - |
| `delimiter` | `string` | Query, Required | - |
| `encodingType` | `string` | Query, Required | - |
| `fetchOwner` | `string` | Query, Required | - |
| `maxKeys` | `string` | Query, Required | - |
| `prefix` | `string` | Query, Required | - |
| `startAfter` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const listType = 2;

const continuationToken = '{{ContinuationToken}}';

const delimiter = '{{Delimiter}}';

const encodingType = '{{EncodingType}}';

const fetchOwner = '{{FetchOwner}}';

const maxKeys = '{{MaxKeys}}';

const prefix = '{{Prefix}}';

const startAfter = '{{StartAfter}}';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await objectsController.objectsV2(
    listType,
    continuationToken,
    delimiter,
    encodingType,
    fetchOwner,
    maxKeys,
    prefix,
    startAfter,
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


# Object 1

Retrieves objects from Amazon S3. To use GET, you must have READ access to the object. If you grant READ access to the anonymous user, you can return the object without using an authorization header.

```ts
async object1(
  xAmzContentSha256: string,
  bucket: string,
  key: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `key` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

const key = 'key0';

try {
  const { result, ...httpResponse } = await objectsController.object1(
    xAmzContentSha256,
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


# Parts

Lists the parts that have been uploaded for a specific multipart upload. This operation must include the upload ID, which you obtain by sending the initiate multipart upload request (see CreateMultipartUpload). This request returns a maximum of 1,000 uploaded parts. The default number of parts returned is 1,000 parts. You can restrict the number of parts returned by specifying the max-parts request parameter. If your multipart upload consists of more than 1,000 parts, the response returns an IsTruncated field with the value of true, and a NextPartNumberMarker element. In subsequent ListParts requests you can include the part-number-marker query string parameter and set its value to the NextPartNumberMarker field value from the previous response.

```ts
async parts(
  maxParts: string,
  partNumberMarker: string,
  uploadId: string,
  xAmzContentSha256: string,
  bucket: string,
  key: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `maxParts` | `string` | Query, Required | - |
| `partNumberMarker` | `string` | Query, Required | - |
| `uploadId` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `key` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const maxParts = '{{MaxParts}}';

const partNumberMarker = '{{PartNumberMarker}}';

const uploadId = '{{UploadId}}';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

const key = 'key0';

try {
  const { result, ...httpResponse } = await objectsController.parts(
    maxParts,
    partNumberMarker,
    uploadId,
    xAmzContentSha256,
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


# Copy Object

Creates a copy of an object that is already stored in Amazon S3.

```ts
async copyObject(
  xAmzContentSha256: string,
  body: string,
  bucket: string,
  key: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `key` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const body = 'hello';

const bucket = 'bucket2';

const key = 'key0';

try {
  const { result, ...httpResponse } = await objectsController.copyObject(
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


# Delete Object

Removes the null version (if there is one) of an object and inserts a delete marker, which becomes the latest version of the object. If there isn't a null version, Amazon S3 does not remove any objects.

```ts
async deleteObject(
  versionId: string,
  xAmzContentSha256: string,
  bucket: string,
  key: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `versionId` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `key` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const versionId = 'VersionId';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

const key = 'key0';

try {
  const { result, ...httpResponse } = await objectsController.deleteObject(
    versionId,
    xAmzContentSha256,
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


# Delete Objects

This operation enables you to delete multiple objects from a bucket using a single HTTP request. If you know the object keys that you want to delete, then this operation provides a suitable alternative to sending individual delete requests, reducing per-request overhead.

```ts
async deleteObjects(
  mDelete: string,
  xAmzContentSha256: string,
  body: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mDelete` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const mDelete = 'delete6';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<Delete xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <Object>\n      <Key>string</Key>\n      <VersionId>string</VersionId>\n   </Object>\n   ...\n   <Quiet>boolean</Quiet>\n</Delete>';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await objectsController.deleteObjects(
    mDelete,
    xAmzContentSha256,
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

