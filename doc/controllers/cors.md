# CORS

```java
CORSController cORSController = client.getCORSController();
```

## Class Name

`CORSController`

## Methods

* [CORS](../../doc/controllers/cors.md#cors)
* [CORS1](../../doc/controllers/cors.md#cors1)
* [CORS2](../../doc/controllers/cors.md#cors2)


# CORS

Sets the cors configuration for your bucket. If the configuration exists, Amazon S3 replaces it.

```java
CompletableFuture<DynamicResponse> cORSAsync(
    final String cors,
    final String contentMD5,
    final String body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cors` | `String` | Query, Required | - |
| `contentMD5` | `String` | Header, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String cors = "cors4";
String contentMD5 = "{{contentMD5}}";
String body = "<CORSConfiguration>\n <CORSRule>\n   <AllowedOrigin>http://www.example.com</AllowedOrigin>\n   <AllowedMethod>PUT</AllowedMethod>\n   <AllowedMethod>POST</AllowedMethod>\n   <AllowedMethod>DELETE</AllowedMethod>\n   <AllowedHeader>*</AllowedHeader>\n </CORSRule>\n <CORSRule>\n   <AllowedOrigin>*</AllowedOrigin>\n   <AllowedMethod>GET</AllowedMethod>\n </CORSRule>\n</CORSConfiguration>";
String bucket = "bucket2";

cORSController.cORSAsync(cors, contentMD5, body, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# CORS1

Deletes the cors configuration information set for the bucket.

```java
CompletableFuture<DynamicResponse> cORS1Async(
    final String cors,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cors` | `String` | Query, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String cors = "cors4";
String bucket = "bucket2";

cORSController.cORS1Async(cors, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# CORS2

```java
CompletableFuture<Void> cORS2Async(
    final String cors,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cors` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String cors = "cors4";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

cORSController.cORS2Async(cors, xAmzContentSha256, bucket).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

