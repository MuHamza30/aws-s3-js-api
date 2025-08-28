# Legal Hold

```ts
const legalHoldController = new LegalHoldController(client);
```

## Class Name

`LegalHoldController`

## Methods

* [Legal Hold](../../doc/controllers/legal-hold.md#legal-hold)
* [Legal Hold 1](../../doc/controllers/legal-hold.md#legal-hold-1)


# Legal Hold

Gets an object's current Legal Hold status. For more information, see Locking Objects.

```ts
async legalHold(
  legalHold: string,
  xAmzContentSha256: string,
  bucket: string,
  key: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `legalHold` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `key` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const legalHold = 'legal-hold2';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

const key = 'key0';

try {
  const { result, ...httpResponse } = await legalHoldController.legalHold(
    legalHold,
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


# Legal Hold 1

Gets an object's current Legal Hold status. For more information, see Locking Objects.

```ts
async legalHold1(
  legalHold: string,
  contentMD5: string,
  body: string,
  bucket: string,
  key: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `legalHold` | `string` | Query, Required | - |
| `contentMD5` | `string` | Header, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `key` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const legalHold = 'legal-hold2';

const contentMD5 = '{{contentMD5}}';

const body = '<LegalHold xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <Status>ON</Status>\n</LegalHold>';

const bucket = 'bucket2';

const key = 'key0';

try {
  const { result, ...httpResponse } = await legalHoldController.legalHold1(
    legalHold,
    contentMD5,
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

