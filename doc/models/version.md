
# Version

## Structure

`Version`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `key` | `string` | Required | - |
| `versionId` | `string` | Required | - |
| `isLatest` | `boolean` | Required | - |
| `lastModified` | `string` | Required | - |
| `eTag` | `string` | Required | - |
| `size` | `number` | Required | - |
| `owner` | [`Owner`](../../doc/models/owner.md) | Required | - |
| `storageClass` | `string` | Required | - |

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

