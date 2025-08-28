
# List Multipart Uploads Result

## Structure

`ListMultipartUploadsResult`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bucket` | `string` | Required | - |
| `keyMarker` | `string` | Required | - |
| `uploadIdMarker` | `string` | Required | - |
| `nextKeyMarker` | `string` | Required | - |
| `nextUploadIdMarker` | `string` | Required | - |
| `maxUploads` | `number` | Required | - |
| `isTruncated` | `boolean` | Required | - |

## Example (as XML)

```xml
<ListMultipartUploadsResult>
  <Bucket>Bucket2</Bucket>
  <KeyMarker>KeyMarker0</KeyMarker>
  <UploadIdMarker>UploadIdMarker0</UploadIdMarker>
  <NextKeyMarker>NextKeyMarker6</NextKeyMarker>
  <NextUploadIdMarker>NextUploadIdMarker8</NextUploadIdMarker>
  <MaxUploads>30</MaxUploads>
  <IsTruncated>false</IsTruncated>
</ListMultipartUploadsResult>
```

