
# Bucket Policy Request

## Structure

`BucketPolicyRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `version` | `string` | Required | - |
| `id` | `string` | Required | - |
| `statement` | [`Statement[]`](../../doc/models/statement.md) | Required | - |

## Example (as JSON)

```json
{
  "Version": "2012-10-17",
  "Id": "S3-Console-Auto-Gen-Policy-1573968487385",
  "Statement": [
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
  ]
}
```

