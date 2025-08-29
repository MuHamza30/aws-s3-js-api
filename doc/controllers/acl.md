# ACL

```java
ACLController aCLController = client.getACLController();
```

## Class Name

`ACLController`

## Methods

* [Bucket ACL](../../doc/controllers/acl.md#bucket-acl)
* [Bucket ACL1](../../doc/controllers/acl.md#bucket-acl1)
* [ACL](../../doc/controllers/acl.md#acl)
* [ACL1](../../doc/controllers/acl.md#acl1)


# Bucket ACL

This implementation of the GET operation uses the acl subresource to return the access control list (ACL) of a bucket. To use GET to return the ACL of the bucket, you must have READ_ACP access to the bucket. If READ_ACP permission is granted to the anonymous user, you can return the ACL of the bucket without using an authorization header.

```java
CompletableFuture<AccessControlPolicy> bucketACLAsync(
    final String acl,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `acl` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

[`AccessControlPolicy`](../../doc/models/access-control-policy.md)

## Example Usage

```java
String acl = "acl0";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

aCLController.bucketACLAsync(acl, xAmzContentSha256, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response *(as XML)*

```xml
<AccessControlPolicy>
  <Owner>
    <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
    <DisplayName>kinlane</DisplayName>
  </Owner>
  <AccessControlList>
    <Grant>
      <Grantee xsi:type="CanonicalUser" xmlns:xsi="http://s3.amazonaws.com/doc/2006-03-01/">
        <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
        <DisplayName>kinlane</DisplayName>
      </Grantee>
      <Permission>FULL_CONTROL</Permission>
    </Grant>
    <Grant>
      <Grantee xsi:type="CanonicalUser" xmlns:xsi="http://s3.amazonaws.com/doc/2006-03-01/">
        <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
        <DisplayName>kinlane</DisplayName>
      </Grantee>
      <Permission>FULL_CONTROL</Permission>
    </Grant>
  </AccessControlList>
</AccessControlPolicy>
```


# Bucket ACL1

Sets the permissions on an existing bucket using access control lists (ACL). For more information, see Using ACLs. To set the ACL of a bucket, you must have WRITE_ACP permission.

```java
CompletableFuture<DynamicResponse> bucketACL1Async(
    final String acl,
    final String body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `acl` | `String` | Query, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String acl = "acl0";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<AccessControlPolicy xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n    <Owner>\n        <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>\n        <DisplayName>kinlane</DisplayName>\n    </Owner>\n    <AccessControlList>\n        <Grant>\n            <Grantee xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instance\" xsi:type=\"CanonicalUser\">\n                <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>\n                <DisplayName>kinlane</DisplayName>\n            </Grantee>\n            <Permission>FULL_CONTROL</Permission>\n        </Grant>\n        <Grant>\n            <Grantee xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instance\" xsi:type=\"CanonicalUser\">\n                <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>\n                <DisplayName>kinlane</DisplayName>\n            </Grantee>\n            <Permission>FULL_CONTROL</Permission>\n        </Grant>\n    </AccessControlList>\n</AccessControlPolicy>";
String bucket = "bucket2";

aCLController.bucketACL1Async(acl, body, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# ACL

Returns the access control list (ACL) of an object. To use this operation, you must have READ_ACP access to the object.

```java
CompletableFuture<AccessControlPolicy1> aCLAsync(
    final String acl,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `acl` | `String` | Query, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

[`AccessControlPolicy1`](../../doc/models/access-control-policy-1.md)

## Example Usage

```java
String acl = "acl0";
String bucket = "bucket2";
String key = "key0";

aCLController.aCLAsync(acl, bucket, key).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response *(as XML)*

```xml
<AccessControlPolicy>
  <Owner>
    <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
    <DisplayName>kinlane</DisplayName>
  </Owner>
  <AccessControlList>
    <Grant>
      <Grantee xsi:type="CanonicalUser" xmlns:xsi="http://s3.amazonaws.com/doc/2006-03-01/">
        <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
        <DisplayName>kinlane</DisplayName>
      </Grantee>
      <Permission>FULL_CONTROL</Permission>
    </Grant>
  </AccessControlList>
</AccessControlPolicy>
```


# ACL1

Returns the access control list (ACL) of an object. To use this operation, you must have READ_ACP access to the object.

```java
CompletableFuture<DynamicResponse> aCL1Async(
    final String acl,
    final String body,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `acl` | `String` | Query, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String acl = "acl0";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<AccessControlPolicy xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n    <Owner>\n        <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>\n        <DisplayName>kinlane</DisplayName>\n    </Owner>\n    <AccessControlList>\n        <Grant>\n            <Grantee xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instance\" xsi:type=\"CanonicalUser\">\n                <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>\n                <DisplayName>kinlane</DisplayName>\n            </Grantee>\n            <Permission>FULL_CONTROL</Permission>\n        </Grant>\n    </AccessControlList>\n</AccessControlPolicy>";
String bucket = "bucket2";
String key = "key0";

aCLController.aCL1Async(acl, body, bucket, key).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

