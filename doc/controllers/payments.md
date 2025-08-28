# Payments

```ts
const paymentsController = new PaymentsController(client);
```

## Class Name

`PaymentsController`

## Methods

* [Bucket Request Payment](../../doc/controllers/payments.md#bucket-request-payment)
* [Bucket Request Payment 1](../../doc/controllers/payments.md#bucket-request-payment-1)


# Bucket Request Payment

Returns the request payment configuration of a bucket. To use this version of the operation, you must be the bucket owner. For more information, see Requester Pays Buckets.

```ts
async bucketRequestPayment(
  requestPayment: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestPayment` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const requestPayment = 'requestPayment4';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await paymentsController.bucketRequestPayment(
    requestPayment,
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
"<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<RequestPaymentConfiguration xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><Payer>Requester</Payer></RequestPaymentConfiguration>"
```


# Bucket Request Payment 1

Sets the request payment configuration for a bucket. By default, the bucket owner pays for downloads from the bucket. This configuration parameter enables the bucket owner (only) to specify that the person requesting the download will be charged for the download.

```ts
async bucketRequestPayment1(
  requestPayment: string,
  body: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestPayment` | `string` | Query, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const requestPayment = 'requestPayment4';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<RequestPaymentConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <Payer>Requester</Payer>\n</RequestPaymentConfiguration>';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await paymentsController.bucketRequestPayment1(
    requestPayment,
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

