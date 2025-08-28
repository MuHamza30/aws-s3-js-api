# Tagging

```ts
const taggingController = new TaggingController(client);
```

## Class Name

`TaggingController`

## Methods

* [Bucket Tagging](../../doc/controllers/tagging.md#bucket-tagging)
* [Bucket Tagging 1](../../doc/controllers/tagging.md#bucket-tagging-1)
* [Delete Bucket Tagging](../../doc/controllers/tagging.md#delete-bucket-tagging)
* [Object Tagging](../../doc/controllers/tagging.md#object-tagging)
* [Tagging](../../doc/controllers/tagging.md#tagging)
* [Delete Object Tagging](../../doc/controllers/tagging.md#delete-object-tagging)


# Bucket Tagging

Returns the tag set associated with the bucket.

```ts
async bucketTagging(
  tagging: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tagging` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const tagging = 'tagging6';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await taggingController.bucketTagging(
    tagging,
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


# Bucket Tagging 1

Sets the tags for a bucket.

```ts
async bucketTagging1(
  tagging: string,
  contentMD5: string,
  body: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tagging` | `string` | Query, Required | - |
| `contentMD5` | `string` | Header, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const tagging = 'tagging6';

const contentMD5 = '{{contentMD5}}';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<Tagging xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <TagSet>\n      <Tag>\n         <Key>Test 123</Key>\n         <Value>Test 123</Value>\n      </Tag>\n   </TagSet>\n</Tagging>';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await taggingController.bucketTagging1(
    tagging,
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


# Delete Bucket Tagging

Deletes the tags from the bucket.

```ts
async deleteBucketTagging(
  tagging: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tagging` | `string` | Query, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const tagging = 'tagging6';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await taggingController.deleteBucketTagging(
    tagging,
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


# Object Tagging

Returns the tag-set of an object. You send the GET request against the tagging subresource associated with the object.

```ts
async objectTagging(
  tagging: string,
  xAmzContentSha256: string,
  bucket: string,
  key: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tagging` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `key` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const tagging = 'tagging6';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

const key = 'key0';

try {
  const { result, ...httpResponse } = await taggingController.objectTagging(
    tagging,
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

## Example Response

```
"<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<Tagging xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><TagSet><Tag><Key>Test</Key><Value>Test</Value></Tag></TagSet></Tagging>"
```


# Tagging

Returns the tag-set of an object. You send the GET request against the tagging subresource associated with the object.

```ts
async tagging(
  tagging: string,
  body: string,
  bucket: string,
  key: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tagging` | `string` | Query, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `key` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const tagging = 'tagging6';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<Tagging xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <TagSet>\n      <Tag>\n         <Key>Test</Key>\n         <Value>Test</Value>\n      </Tag>\n   </TagSet>\n</Tagging>';

const bucket = 'bucket2';

const key = 'key0';

try {
  const { result, ...httpResponse } = await taggingController.tagging(
    tagging,
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


# Delete Object Tagging

Removes the entire tag set from the specified object. For more information about managing object tags, see Object Tagging.

```ts
async deleteObjectTagging(
  tagging: string,
  xAmzContentSha256: string,
  bucket: string,
  key: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tagging` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `key` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const tagging = 'tagging6';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

const key = 'key0';

try {
  const { result, ...httpResponse } = await taggingController.deleteObjectTagging(
    tagging,
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

