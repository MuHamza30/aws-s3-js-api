# Misc

```ts
const miscController = new MiscController(client);
```

## Class Name

`MiscController`


# Root

```ts
async root(
  xAmzContentSha256: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

try {
  const { result, ...httpResponse } = await miscController.root(xAmzContentSha256);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

