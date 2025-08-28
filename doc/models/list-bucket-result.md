
# List Bucket Result

## Structure

`ListBucketResult`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Required | - |
| `prefix` | `string` | Required | - |
| `marker` | `string` | Required | - |
| `maxKeys` | `number` | Required | - |
| `isTruncated` | `boolean` | Required | - |

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

