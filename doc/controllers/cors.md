# CORS

```ts
const cORSController = new CORSController(client);
```

## Class Name

`CORSController`

## Methods

* [CORS](../../doc/controllers/cors.md#cors)
* [CORS1](../../doc/controllers/cors.md#cors1)
* [CORS2](../../doc/controllers/cors.md#cors2)


# CORS

Sets the cors configuration for your bucket. If the configuration exists, Amazon S3 replaces it.

```ts
async cORS(
  cors: string,
  contentMD5: string,
  body: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cors` | `string` | Query, Required | - |
| `contentMD5` | `string` | Header, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const cors = 'cors4';

const contentMD5 = '{{contentMD5}}';

const body = '<CORSConfiguration>\n <CORSRule>\n   <AllowedOrigin>http://www.example.com</AllowedOrigin>\n   <AllowedMethod>PUT</AllowedMethod>\n   <AllowedMethod>POST</AllowedMethod>\n   <AllowedMethod>DELETE</AllowedMethod>\n   <AllowedHeader>*</AllowedHeader>\n </CORSRule>\n <CORSRule>\n   <AllowedOrigin>*</AllowedOrigin>\n   <AllowedMethod>GET</AllowedMethod>\n </CORSRule>\n</CORSConfiguration>';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await cORSController.cORS(
    cors,
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


# CORS1

Deletes the cors configuration information set for the bucket.

```ts
async cORS1(
  cors: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cors` | `string` | Query, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const cors = 'cors4';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await cORSController.cORS1(
    cors,
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


# CORS2

```ts
async cORS2(
  cors: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cors` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const cors = 'cors4';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await cORSController.cORS2(
    cors,
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

