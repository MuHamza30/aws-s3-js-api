
# List Versions Result

## Structure

`ListVersionsResult`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Required | - |
| `prefix` | `string` | Required | - |
| `keyMarker` | `string` | Required | - |
| `versionIdMarker` | `string` | Required | - |
| `maxKeys` | `number` | Required | - |
| `isTruncated` | `boolean` | Required | - |
| `version` | [`Version[]`](../../doc/models/version.md) | Required | - |

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

