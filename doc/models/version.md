
# Version

## Structure

`Version`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Key` | `String` | Required | - | String getKey() | setKey(String key) |
| `VersionId` | `String` | Required | - | String getVersionId() | setVersionId(String versionId) |
| `IsLatest` | `boolean` | Required | - | boolean getIsLatest() | setIsLatest(boolean isLatest) |
| `LastModified` | `String` | Required | - | String getLastModified() | setLastModified(String lastModified) |
| `ETag` | `String` | Required | - | String getETag() | setETag(String eTag) |
| `Size` | `int` | Required | - | int getSize() | setSize(int size) |
| `Owner` | [`Owner`](../../doc/models/owner.md) | Required | - | Owner getOwner() | setOwner(Owner owner) |
| `StorageClass` | `String` | Required | - | String getStorageClass() | setStorageClass(String storageClass) |

## Example (as XML)

```xml
<Version>
  <Key>Key8</Key>
  <VersionId>VersionId6</VersionId>
  <IsLatest>false</IsLatest>
  <LastModified>LastModified2</LastModified>
  <ETag>ETag0</ETag>
  <Size>118</Size>
  <Owner>
    <ID>ID4</ID>
    <DisplayName>DisplayName6</DisplayName>
  </Owner>
  <StorageClass>StorageClass4</StorageClass>
</Version>
```

