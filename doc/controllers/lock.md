# Lock

```java
LockController lockController = client.getLockController();
```

## Class Name

`LockController`

## Methods

* [Object Lock Configuration](../../doc/controllers/lock.md#object-lock-configuration)
* [Object Lock Configuration Copy](../../doc/controllers/lock.md#object-lock-configuration-copy)


# Object Lock Configuration

Gets the Object Lock configuration for a bucket. The rule specified in the Object Lock configuration will be applied by default to every new object placed in the specified bucket. For more information, see Locking Objects.

```java
CompletableFuture<ListAllMyBucketsResult> objectLockConfigurationAsync(
    final String objectLock,
    final String xAmzContentSha256)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `objectLock` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |

## Response Type

[`ListAllMyBucketsResult`](../../doc/models/list-all-my-buckets-result.md)

## Example Usage

```java
String objectLock = "object-lock2";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";

lockController.objectLockConfigurationAsync(objectLock, xAmzContentSha256).thenAccept(result -> {
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

```java
CompletableFuture<ListAllMyBucketsResult> objectLockConfigurationCopyAsync(
    final String objectLock,
    final String xAmzContentSha256)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `objectLock` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |

## Response Type

[`ListAllMyBucketsResult`](../../doc/models/list-all-my-buckets-result.md)

## Example Usage

```java
String objectLock = "object-lock2";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";

lockController.objectLockConfigurationCopyAsync(objectLock, xAmzContentSha256).thenAccept(result -> {
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

