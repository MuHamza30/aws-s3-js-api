
# Error Exception

## Structure

`ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Code` | `String` | Required | - | String getCode() | setCode(String code) |
| `Message` | `String` | Required | - | String getMessageField() | setMessageField(String messageField) |
| `BucketName` | `String` | Required | - | String getBucketName() | setBucketName(String bucketName) |
| `RequestId` | `String` | Required | - | String getRequestId() | setRequestId(String requestId) |
| `HostId` | `String` | Required | - | String getHostId() | setHostId(String hostId) |

## Example (as JSON)

```json
{
  "Code": "Code4",
  "Message": "Message0",
  "BucketName": "BucketName8",
  "RequestId": "RequestId6",
  "HostId": "HostId4"
}
```

