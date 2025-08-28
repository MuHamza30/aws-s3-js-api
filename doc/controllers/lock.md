# Lock

```ts
const lockController = new LockController(client);
```

## Class Name

`LockController`

## Methods

* [Object Lock Configuration](../../doc/controllers/lock.md#object-lock-configuration)
* [Object Lock Configuration Copy](../../doc/controllers/lock.md#object-lock-configuration-copy)


# Object Lock Configuration

Gets the Object Lock configuration for a bucket. The rule specified in the Object Lock configuration will be applied by default to every new object placed in the specified bucket. For more information, see Locking Objects.

```ts
async objectLockConfiguration(
  objectLock: string,
  xAmzContentSha256: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ListAllMyBucketsResult>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `objectLock` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ListAllMyBucketsResult`](../../doc/models/list-all-my-buckets-result.md).

## Example Usage

```ts
const objectLock = 'object-lock2';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

try {
  const { result, ...httpResponse } = await lockController.objectLockConfiguration(
    objectLock,
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

## Example Response *(as XML)*

```xml
<ListAllMyBucketsResult>
  <Owner>
    <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
    <DisplayName>kinlane</DisplayName>
  </Owner>
  <Buckets>
    <Bucket>
      <Name>working-demo-2</Name>
      <CreationDate>2019-11-17T04:45:13Z</CreationDate>
    </Bucket>
  </Buckets>
</ListAllMyBucketsResult>
```


# Object Lock Configuration Copy

Gets the Object Lock configuration for a bucket. The rule specified in the Object Lock configuration will be applied by default to every new object placed in the specified bucket. For more information, see Locking Objects.

```ts
async objectLockConfigurationCopy(
  objectLock: string,
  xAmzContentSha256: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ListAllMyBucketsResult>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `objectLock` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ListAllMyBucketsResult`](../../doc/models/list-all-my-buckets-result.md).

## Example Usage

```ts
const objectLock = 'object-lock2';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

try {
  const { result, ...httpResponse } = await lockController.objectLockConfigurationCopy(
    objectLock,
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

## Example Response *(as XML)*

```xml
<ListAllMyBucketsResult>
  <Owner>
    <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
    <DisplayName>kinlane</DisplayName>
  </Owner>
  <Buckets>
    <Bucket>
      <Name>working-demo-2</Name>
      <CreationDate>2019-11-17T04:45:13Z</CreationDate>
    </Bucket>
  </Buckets>
</ListAllMyBucketsResult>
```

