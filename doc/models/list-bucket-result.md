
# List Bucket Result

## Structure

`ListBucketResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Name` | `String` | Required | - | String getName() | setName(String name) |
| `Prefix` | `String` | Required | - | String getPrefix() | setPrefix(String prefix) |
| `Marker` | `String` | Required | - | String getMarker() | setMarker(String marker) |
| `MaxKeys` | `int` | Required | - | int getMaxKeys() | setMaxKeys(int maxKeys) |
| `IsTruncated` | `boolean` | Required | - | boolean getIsTruncated() | setIsTruncated(boolean isTruncated) |

## Example (as XML)

```xml
<ListBucketResult>
  <Name>Name2</Name>
  <Prefix>Prefix6</Prefix>
  <Marker>Marker2</Marker>
  <MaxKeys>172</MaxKeys>
  <IsTruncated>false</IsTruncated>
</ListBucketResult>
```

