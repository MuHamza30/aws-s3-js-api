
# Statement

## Structure

`Statement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Sid` | `String` | Required | - | String getSid() | setSid(String sid) |
| `Effect` | `String` | Required | - | String getEffect() | setEffect(String effect) |
| `Principal` | [`Principal`](../../doc/models/principal.md) | Required | - | Principal getPrincipal() | setPrincipal(Principal principal) |
| `Action` | `String` | Required | - | String getAction() | setAction(String action) |
| `Resource` | `String` | Required | - | String getResource() | setResource(String resource) |
| `Condition` | [`Condition`](../../doc/models/condition.md) | Required | - | Condition getCondition() | setCondition(Condition condition) |

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

