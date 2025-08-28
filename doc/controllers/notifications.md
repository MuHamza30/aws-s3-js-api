# Notifications

```ts
const notificationsController = new NotificationsController(client);
```

## Class Name

`NotificationsController`

## Methods

* [Bucket Notification C Onfiguration](../../doc/controllers/notifications.md#bucket-notification-c-onfiguration)
* [Bucket Notification C Onfiguration 1](../../doc/controllers/notifications.md#bucket-notification-c-onfiguration-1)


# Bucket Notification C Onfiguration

Returns the notification configuration of a bucket.

```ts
async bucketNotificationCOnfiguration(
  notification: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `notification` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const notification = 'notification2';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await notificationsController.bucketNotificationCOnfiguration(
    notification,
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


# Bucket Notification C Onfiguration 1

Enables notifications of specified events for a bucket. For more information about event notifications, see Configuring Event Notifications.

```ts
async bucketNotificationCOnfiguration1(
  notification: string,
  body: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `notification` | `string` | Query, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```ts
const notification = 'notification2';

const body = '<NotificationConfiguration>\n  <CloudFunctionConfiguration>\n    <Id>ObjectCreatedEvents</Id>\n    <CloudFunction>arn:aws:lambda:us-west-2:35667example:function:CreateThumbnail</CloudFunction>\n    <Event>s3:ObjectCreated:*</Event>\n  </CloudFunctionConfiguration>\n</NotificationConfiguration>';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await notificationsController.bucketNotificationCOnfiguration1(
    notification,
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

