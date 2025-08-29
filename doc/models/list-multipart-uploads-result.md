
# List Multipart Uploads Result

## Structure

`ListMultipartUploadsResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Bucket` | `String` | Required | - | String getBucket() | setBucket(String bucket) |
| `KeyMarker` | `String` | Required | - | String getKeyMarker() | setKeyMarker(String keyMarker) |
| `UploadIdMarker` | `String` | Required | - | String getUploadIdMarker() | setUploadIdMarker(String uploadIdMarker) |
| `NextKeyMarker` | `String` | Required | - | String getNextKeyMarker() | setNextKeyMarker(String nextKeyMarker) |
| `NextUploadIdMarker` | `String` | Required | - | String getNextUploadIdMarker() | setNextUploadIdMarker(String nextUploadIdMarker) |
| `MaxUploads` | `int` | Required | - | int getMaxUploads() | setMaxUploads(int maxUploads) |
| `IsTruncated` | `boolean` | Required | - | boolean getIsTruncated() | setIsTruncated(boolean isTruncated) |

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

