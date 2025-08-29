# Notifications

```java
NotificationsController notificationsController = client.getNotificationsController();
```

## Class Name

`NotificationsController`

## Methods

* [Bucket Notification C Onfiguration](../../doc/controllers/notifications.md#bucket-notification-c-onfiguration)
* [Bucket Notification C Onfiguration 1](../../doc/controllers/notifications.md#bucket-notification-c-onfiguration-1)


# Bucket Notification C Onfiguration

Returns the notification configuration of a bucket.

```java
CompletableFuture<Void> bucketNotificationCOnfigurationAsync(
    final String notification,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `notification` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String notification = "notification2";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

notificationsController.bucketNotificationCOnfigurationAsync(notification, xAmzContentSha256, bucket).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Bucket Notification C Onfiguration 1

Enables notifications of specified events for a bucket. For more information about event notifications, see Configuring Event Notifications.

```java
CompletableFuture<Void> bucketNotificationCOnfiguration1Async(
    final String notification,
    final String body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `notification` | `String` | Query, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String notification = "notification2";
String body = "<NotificationConfiguration>\n  <CloudFunctionConfiguration>\n    <Id>ObjectCreatedEvents</Id>\n    <CloudFunction>arn:aws:lambda:us-west-2:35667example:function:CreateThumbnail</CloudFunction>\n    <Event>s3:ObjectCreated:*</Event>\n  </CloudFunctionConfiguration>\n</NotificationConfiguration>";
String bucket = "bucket2";

notificationsController.bucketNotificationCOnfiguration1Async(notification, body, bucket).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

