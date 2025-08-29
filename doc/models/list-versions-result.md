
# List Versions Result

## Structure

`ListVersionsResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Name` | `String` | Required | - | String getName() | setName(String name) |
| `Prefix` | `String` | Required | - | String getPrefix() | setPrefix(String prefix) |
| `KeyMarker` | `String` | Required | - | String getKeyMarker() | setKeyMarker(String keyMarker) |
| `VersionIdMarker` | `String` | Required | - | String getVersionIdMarker() | setVersionIdMarker(String versionIdMarker) |
| `MaxKeys` | `int` | Required | - | int getMaxKeys() | setMaxKeys(int maxKeys) |
| `IsTruncated` | `boolean` | Required | - | boolean getIsTruncated() | setIsTruncated(boolean isTruncated) |
| `Version` | [`List<Version>`](../../doc/models/version.md) | Required | - | List<Version> getVersion() | setVersion(List<Version> version) |

## Example (as XML)

```xml
<ListVersionsResult>
  <Name>Name8</Name>
  <Prefix>Prefix2</Prefix>
  <KeyMarker>KeyMarker6</KeyMarker>
  <VersionIdMarker>VersionIdMarker0</VersionIdMarker>
  <MaxKeys>36</MaxKeys>
  <IsTruncated>false</IsTruncated>
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
</ListVersionsResult>
```

