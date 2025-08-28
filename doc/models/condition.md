
# Condition

## Structure

`Condition`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `stringEquals` | [`StringEquals`](../../doc/models/string-equals.md) | Required | - |
| `arnLike` | [`ArnLike`](../../doc/models/arn-like.md) | Required | - |

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

