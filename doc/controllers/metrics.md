# Metrics

```ts
const metricsController = new MetricsController(client);
```

## Class Name

`MetricsController`

## Methods

* [Bucket Metrics Configuration](../../doc/controllers/metrics.md#bucket-metrics-configuration)
* [Bucket Metrics Configuration 1](../../doc/controllers/metrics.md#bucket-metrics-configuration-1)
* [List Bucket Metrics Configurations](../../doc/controllers/metrics.md#list-bucket-metrics-configurations)
* [Delete Bucket Metrics Configuration](../../doc/controllers/metrics.md#delete-bucket-metrics-configuration)


# Bucket Metrics Configuration

Gets a metrics configuration (specified by the metrics configuration ID) from the bucket. Note that this doesn't include the daily storage metrics.

```ts
async bucketMetricsConfiguration(
  metrics: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `metrics` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const metrics = 'metrics8';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await metricsController.bucketMetricsConfiguration(
    metrics,
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
"<?xml version=\"1.0\" encoding=\"UTF-8\"?><ListMetricsConfigurationsResult xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><IsTruncated>false</IsTruncated></ListMetricsConfigurationsResult>"
```


# Bucket Metrics Configuration 1

Sets a metrics configuration (specified by the metrics configuration ID) for the bucket. You can have up to 1,000 metrics configurations per bucket. If you're updating an existing metrics configuration, note that this is a full replacement of the existing metrics configuration. If you don't include the elements you want to keep, they are erased.

```ts
async bucketMetricsConfiguration1(
  metrics: string,
  id: string,
  body: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `metrics` | `string` | Query, Required | - |
| `id` | `string` | Query, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const metrics = 'metrics8';

const id = '{{Id}}';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<MetricsConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n   <Id>test1</Id>\n   <Filter>\n      <And>\n         <Prefix>string</Prefix>\n         <Tag>\n            <Key>string</Key>\n            <Value>string</Value>\n         </Tag>\n      </And>\n      <Prefix>string</Prefix>\n      <Tag>\n         <Key>string</Key>\n         <Value>string</Value>\n      </Tag>\n   </Filter>\n</MetricsConfiguration>';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await metricsController.bucketMetricsConfiguration1(
    metrics,
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


# List Bucket Metrics Configurations

Lists the metrics configurations for the bucket. The metrics configurations are only for the request metrics of the bucket and do not provide information on daily storage metrics. You can have up to 1,000 configurations per bucket.

```ts
async listBucketMetricsConfigurations(
  metrics: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `metrics` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const metrics = 'metrics8';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await metricsController.listBucketMetricsConfigurations(
    metrics,
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
"<?xml version=\"1.0\" encoding=\"UTF-8\"?><ListMetricsConfigurationsResult xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><IsTruncated>false</IsTruncated></ListMetricsConfigurationsResult>"
```


# Delete Bucket Metrics Configuration

Deletes a metrics configuration for the Amazon CloudWatch request metrics (specified by the metrics configuration ID) from the bucket. Note that this doesn't include the daily storage metrics.

```ts
async deleteBucketMetricsConfiguration(
  metrics: string,
  id: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `metrics` | `string` | Query, Required | - |
| `id` | `string` | Query, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const metrics = 'metrics8';

const id = 'test';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await metricsController.deleteBucketMetricsConfiguration(
    metrics,
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

