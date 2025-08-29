# Inventory

```java
InventoryController inventoryController = client.getInventoryController();
```

## Class Name

`InventoryController`

## Methods

* [Bucket Inventory Configuration](../../doc/controllers/inventory.md#bucket-inventory-configuration)
* [Delete Bucket Inventory Configuration](../../doc/controllers/inventory.md#delete-bucket-inventory-configuration)
* [Bucket Inventory Configuration 1](../../doc/controllers/inventory.md#bucket-inventory-configuration-1)


# Bucket Inventory Configuration

Returns an inventory configuration (identified by the inventory configuration ID) from the bucket.

```java
CompletableFuture<String> bucketInventoryConfigurationAsync(
    final String inventory,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `inventory` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`String`

## Example Usage

```java
String inventory = "inventory4";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

inventoryController.bucketInventoryConfigurationAsync(inventory, xAmzContentSha256, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response

```
"<?xml version=\"1.0\" encoding=\"UTF-8\"?><ListInventoryConfigurationsResult xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><InventoryConfiguration><Id>test-inventory</Id><IsEnabled>true</IsEnabled><Destination><S3BucketDestination><Format>CSV</Format><Bucket>arn:aws:s3:::working-demo-2</Bucket><Encryption><SSE-S3/></Encryption></S3BucketDestination></Destination><Schedule><Frequency>Daily</Frequency></Schedule><IncludedObjectVersions>Current</IncludedObjectVersions><OptionalFields/></InventoryConfiguration><IsTruncated>false</IsTruncated></ListInventoryConfigurationsResult>"
```


# Delete Bucket Inventory Configuration

Deletes an inventory configuration (identified by the inventory ID) from the bucket.

```java
CompletableFuture<Void> deleteBucketInventoryConfigurationAsync(
    final String inventory,
    final String id,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `inventory` | `String` | Query, Required | - |
| `id` | `String` | Query, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String inventory = "inventory4";
String id = "test-inventory";
String bucket = "bucket2";

inventoryController.deleteBucketInventoryConfigurationAsync(inventory, id, bucket).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Bucket Inventory Configuration 1

This implementation of the PUT operation adds an inventory configuration (identified by the inventory ID) to the bucket. You can have up to 1,000 inventory configurations per bucket.

```java
CompletableFuture<Void> bucketInventoryConfiguration1Async(
    final String inventory,
    final String id,
    final String body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `inventory` | `String` | Query, Required | - |
| `id` | `String` | Query, Required | - |
| `body` | `String` | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String inventory = "inventory4";
String id = "{{Id}}";
String body = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<InventoryConfiguration xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\">\n   <Destination>\n      <S3BucketDestination>\n         <AccountId>string</AccountId>\n         <Bucket>string</Bucket>\n         <Encryption>\n            <SSE-KMS>\n               <KeyId>string</KeyId>\n            </SSE-KMS>\n            <SSE-S3>\n            </SSE-S3>\n         </Encryption>\n         <Format>string</Format>\n         <Prefix>string</Prefix>\n      </S3BucketDestination>\n   </Destination>\n   <IsEnabled>boolean</IsEnabled>\n   <Filter>\n      <Prefix>string</Prefix>\n   </Filter>\n   <Id>test-inventory</Id>\n   <IncludedObjectVersions>string</IncludedObjectVersions>\n   <OptionalFields>\n      <Field>string</Field>\n   </OptionalFields>\n   <Schedule>\n      <Frequency>string</Frequency>\n   </Schedule>\n</InventoryConfiguration>";
String bucket = "bucket2";

inventoryController.bucketInventoryConfiguration1Async(inventory, id, body, bucket).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

