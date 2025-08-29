
# List Bucket Result 1

## Structure

`ListBucketResult1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Name` | `String` | Required | - | String getName() | setName(String name) |
| `Prefix` | `String` | Required | - | String getPrefix() | setPrefix(String prefix) |
| `Marker` | `String` | Required | - | String getMarker() | setMarker(String marker) |
| `MaxKeys` | `int` | Required | - | int getMaxKeys() | setMaxKeys(int maxKeys) |
| `IsTruncated` | `boolean` | Required | - | boolean getIsTruncated() | setIsTruncated(boolean isTruncated) |
| `Contents` | [`List<Contents>`](../../doc/models/contents.md) | Required | - | List<Contents> getContents() | setContents(List<Contents> contents) |

## Example (as XML)

```xml
<ListBucketResult>
  <Name>Name6</Name>
  <Prefix>Prefix0</Prefix>
  <Marker>Marker6</Marker>
  <MaxKeys>208</MaxKeys>
  <IsTruncated>false</IsTruncated>
  <Contents>
    <Key>Key4</Key>
    <LastModified>LastModified8</LastModified>
    <ETag>ETag6</ETag>
    <Size>92</Size>
    <Owner>
      <ID>ID4</ID>
      <DisplayName>DisplayName6</DisplayName>
    </Owner>
    <StorageClass>StorageClass0</StorageClass>
  </Contents>
</ListBucketResult>
```

