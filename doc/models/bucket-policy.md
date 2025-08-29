
# Bucket Policy

## Structure

`BucketPolicy`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Version` | `String` | Required | - | String getVersion() | setVersion(String version) |
| `Id` | `String` | Required | - | String getId() | setId(String id) |
| `Statement` | [`List<Statement>`](../../doc/models/statement.md) | Required | - | List<Statement> getStatement() | setStatement(List<Statement> statement) |

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

