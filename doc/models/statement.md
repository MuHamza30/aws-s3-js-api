
# Statement

## Structure

`Statement`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sid` | `string` | Required | - |
| `effect` | `string` | Required | - |
| `principal` | [`Principal`](../../doc/models/principal.md) | Required | - |
| `action` | `string` | Required | - |
| `resource` | `string` | Required | - |
| `condition` | [`Condition`](../../doc/models/condition.md) | Required | - |

## Example (as JSON)

```json
{
  "Sid": "S3PolicyStmt-DO-NOT-MODIFY-1573968487385",
  "Effect": "Allow",
  "Principal": {
    "Service": "s3.amazonaws.com"
  },
  "Action": "s3:PutObject",
  "Resource": "arn:aws:s3:::working-demo-2/*",
  "Condition": {
    "StringEquals": {
      "aws:SourceAccount": "879370021840",
      "s3:x-amz-acl": "bucket-owner-full-control"
    },
    "ArnLike": {
      "aws:SourceArn": "arn:aws:s3:::working-demo-2"
    }
  }
}
```

