# Website

```java
WebsiteController websiteController = client.getWebsiteController();
```

## Class Name

`WebsiteController`

## Methods

* [Website](../../doc/controllers/website.md#website)
* [Website 1](../../doc/controllers/website.md#website-1)
* [Website 2](../../doc/controllers/website.md#website-2)


# Website

Returns the website configuration for a bucket. To host website on Amazon S3, you can configure a bucket as website by adding a website configuration. For more information about hosting websites, see Hosting Websites on Amazon S3.

```java
CompletableFuture<Void> websiteAsync(
    final String website,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `website` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String website = "website4";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

websiteController.websiteAsync(website, xAmzContentSha256, bucket).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Website 1

Sets the configuration of the website that is specified in the website subresource. To configure a bucket as a website, you can add this subresource on the bucket with website configuration information such as the file name of the index document and any redirect rules.

```java
CompletableFuture<DynamicResponse> website1Async(
    final String website,
    final String contentMD5,
    final String body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `website` | `String` | Query, Required | - |
| `contentMD5` | `String` | Header, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String website = "website4";
String contentMD5 = "{{contentMD5}}";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<WebsiteConfiguration xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n    <IndexDocument>\n        <Suffix>index.html</Suffix>\n    </IndexDocument>\n    <ErrorDocument>\n        <Key>error.html</Key>\n    </ErrorDocument>\n</WebsiteConfiguration>";
String bucket = "bucket2";

websiteController.website1Async(website, contentMD5, body, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Website 2

This operation removes the website configuration for a bucket. Amazon S3 returns a 200 OK response upon successfully deleting a website configuration on the specified bucket. You will get a 200 OK response if the website configuration you are trying to delete does not exist on the bucket. Amazon S3 returns a 404 response if the bucket specified in the request does not exist.

```java
CompletableFuture<DynamicResponse> website2Async(
    final String website,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `website` | `String` | Query, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String website = "website4";
String bucket = "bucket2";

websiteController.website2Async(website, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

