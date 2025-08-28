# Analytics

```ts
const analyticsController = new AnalyticsController(client);
```

## Class Name

`AnalyticsController`

## Methods

* [Bucket Analytics](../../doc/controllers/analytics.md#bucket-analytics)
* [Bucket Analytics Configurations](../../doc/controllers/analytics.md#bucket-analytics-configurations)
* [Bucket Analytics Configurations 1](../../doc/controllers/analytics.md#bucket-analytics-configurations-1)
* [Delete Bucket Analytics Configuration](../../doc/controllers/analytics.md#delete-bucket-analytics-configuration)


# Bucket Analytics

This implementation of the GET operation returns an analytics configuration (identified by the analytics configuration ID) from the bucket.

```ts
async bucketAnalytics(
  analytics: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `analytics` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const analytics = 'analytics2';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await analyticsController.bucketAnalytics(
    analytics,
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
"<ListBucketAnalyticsConfigurationsResult xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><IsTruncated>false</IsTruncated></ListBucketAnalyticsConfigurationsResult>"
```


# Bucket Analytics Configurations

Lists the analytics configurations for the bucket. You can have up to 1,000 analytics configurations per bucket.

```ts
async bucketAnalyticsConfigurations(
  analytics: string,
  id: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `analytics` | `string` | Query, Required | - |
| `id` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const analytics = 'analytics2';

const id = 'test';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await analyticsController.bucketAnalyticsConfigurations(
    analytics,
    id,
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
"<ListBucketAnalyticsConfigurationsResult xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><IsTruncated>false</IsTruncated></ListBucketAnalyticsConfigurationsResult>"
```


# Bucket Analytics Configurations 1

Sets an analytics configuration for the bucket (specified by the analytics configuration ID). You can have up to 1,000 analytics configurations per bucket.

```ts
async bucketAnalyticsConfigurations1(
  analytics: string,
  id: string,
  body: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `analytics` | `string` | Query, Required | - |
| `id` | `string` | Query, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const analytics = 'analytics2';

const id = 'test2';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<AnalyticsConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <Id>test</Id>\n   <Filter>\n      <And>\n         <Prefix>test/</Prefix>\n         <Tag>\n            <Key>string</Key>\n            <Value>string</Value>\n         </Tag>\n      </And>\n      <Prefix>string</Prefix>\n      <Tag>\n         <Key>string</Key>\n         <Value>string</Value>\n      </Tag>\n   </Filter>\n   <StorageClassAnalysis>\n      <DataExport>\n         <Destination>\n            <S3BucketDestination>\n               <Bucket>arn:aws:s3:::working-demo-2</Bucket>\n               <Format>CSV</Format>\n               <Prefix>destination-prefix</Prefix>\n            </S3BucketDestination>\n         </Destination>\n         <OutputSchemaVersion>string</OutputSchemaVersion>\n      </DataExport>\n   </StorageClassAnalysis>\n</AnalyticsConfiguration>';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await analyticsController.bucketAnalyticsConfigurations1(
    analytics,
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


# Delete Bucket Analytics Configuration

Deletes an analytics configuration for the bucket (specified by the analytics configuration ID).

```ts
async deleteBucketAnalyticsConfiguration(
  analytics: string,
  id: string,
  body: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `analytics` | `string` | Query, Required | - |
| `id` | `string` | Query, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const analytics = 'analytics2';

const id = 'test';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<CreateBucketConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <LocationConstraint>us-west-1</LocationConstraint>\n</CreateBucketConfiguration>';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await analyticsController.deleteBucketAnalyticsConfiguration(
    analytics,
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

