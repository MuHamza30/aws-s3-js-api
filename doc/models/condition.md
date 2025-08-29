
# Condition

## Structure

`Condition`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `StringEquals` | [`StringEquals`](../../doc/models/string-equals.md) | Required | - | StringEquals getStringEquals() | setStringEquals(StringEquals stringEquals) |
| `ArnLike` | [`ArnLike`](../../doc/models/arn-like.md) | Required | - | ArnLike getArnLike() | setArnLike(ArnLike arnLike) |

## Example (as JSON)

```json
{
  "StringEquals": {
    "aws:SourceAccount": "879370021840",
    "s3:x-amz-acl": "bucket-owner-full-control"
  },
  "ArnLike": {
    "aws:SourceArn": "arn:aws:s3:::working-demo-2"
  }
}
```

