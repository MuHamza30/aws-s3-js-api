# Inventory

```ts
const inventoryController = new InventoryController(client);
```

## Class Name

`InventoryController`

## Methods

* [Bucket Inventory Configuration](../../doc/controllers/inventory.md#bucket-inventory-configuration)
* [Delete Bucket Inventory Configuration](../../doc/controllers/inventory.md#delete-bucket-inventory-configuration)
* [Bucket Inventory Configuration 1](../../doc/controllers/inventory.md#bucket-inventory-configuration-1)


# Bucket Inventory Configuration

Returns an inventory configuration (identified by the inventory configuration ID) from the bucket.

```ts
async bucketInventoryConfiguration(
  inventory: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `inventory` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const inventory = 'inventory4';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await inventoryController.bucketInventoryConfiguration(
    inventory,
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
"<?xml version=\"1.0\" encoding=\"UTF-8\"?><ListInventoryConfigurationsResult xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><InventoryConfiguration><Id>test-inventory</Id><IsEnabled>true</IsEnabled><Destination><S3BucketDestination><Format>CSV</Format><Bucket>arn:aws:s3:::working-demo-2</Bucket><Encryption><SSE-S3/></Encryption></S3BucketDestination></Destination><Schedule><Frequency>Daily</Frequency></Schedule><IncludedObjectVersions>Current</IncludedObjectVersions><OptionalFields/></InventoryConfiguration><IsTruncated>false</IsTruncated></ListInventoryConfigurationsResult>"
```


# Delete Bucket Inventory Configuration

Deletes an inventory configuration (identified by the inventory ID) from the bucket.

```ts
async deleteBucketInventoryConfiguration(
  inventory: string,
  id: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `inventory` | `string` | Query, Required | - |
| `id` | `string` | Query, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const inventory = 'inventory4';

const id = 'test-inventory';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await inventoryController.deleteBucketInventoryConfiguration(
    inventory,
    id,
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


# Bucket Inventory Configuration 1

This implementation of the PUT operation adds an inventory configuration (identified by the inventory ID) to the bucket. You can have up to 1,000 inventory configurations per bucket.

```ts
async bucketInventoryConfiguration1(
  inventory: string,
  id: string,
  body: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `inventory` | `string` | Query, Required | - |
| `id` | `string` | Query, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const inventory = 'inventory4';

const id = '{{Id}}';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<InventoryConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <Destination>\n      <S3BucketDestination>\n         <AccountId>string</AccountId>\n         <Bucket>string</Bucket>\n         <Encryption>\n            <SSE-KMS>\n               <KeyId>string</KeyId>\n            </SSE-KMS>\n            <SSE-S3>\n            </SSE-S3>\n         </Encryption>\n         <Format>string</Format>\n         <Prefix>string</Prefix>\n      </S3BucketDestination>\n   </Destination>\n   <IsEnabled>boolean</IsEnabled>\n   <Filter>\n      <Prefix>string</Prefix>\n   </Filter>\n   <Id>test-inventory</Id>\n   <IncludedObjectVersions>string</IncludedObjectVersions>\n   <OptionalFields>\n      <Field>string</Field>\n   </OptionalFields>\n   <Schedule>\n      <Frequency>string</Frequency>\n   </Schedule>\n</InventoryConfiguration>';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await inventoryController.bucketInventoryConfiguration1(
    inventory,
    id,
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

