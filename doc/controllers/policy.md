# Policy

```java
PolicyController policyController = client.getPolicyController();
```

## Class Name

`PolicyController`

## Methods

* [Bucket Policy](../../doc/controllers/policy.md#bucket-policy)
* [Bucket Policy 1](../../doc/controllers/policy.md#bucket-policy-1)
* [Bucket Policy Status](../../doc/controllers/policy.md#bucket-policy-status)
* [Delete Bucket Policy](../../doc/controllers/policy.md#delete-bucket-policy)


# Bucket Policy

Returns the policy of a specified bucket. If you are using an identity other than the root user of the AWS account that owns the bucket, the calling identity must have the GetBucketPolicy permissions on the specified bucket and belong to the bucket owner's account in order to use this operation.

```java
CompletableFuture<BucketPolicy> bucketPolicyAsync(
    final String policy,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `policy` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

[`BucketPolicy`](../../doc/models/bucket-policy.md)

## Example Usage

```java
String policy = "policy4";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

policyController.bucketPolicyAsync(policy, xAmzContentSha256, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response *(as JSON)*

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


# Bucket Policy 1

Applies an Amazon S3 bucket policy to an Amazon S3 bucket. If you are using an identity other than the root user of the AWS account that owns the bucket, the calling identity must have the PutBucketPolicy permissions on the specified bucket and belong to the bucket owner's account in order to use this operation.

```java
CompletableFuture<DynamicResponse> bucketPolicy1Async(
    final String policy,
    final String contentMD5,
    final String xAmzConfirmRemoveSelfBucketAccess,
    final BucketPolicyRequest body,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `policy` | `String` | Query, Required | - |
| `contentMD5` | `String` | Header, Required | - |
| `xAmzConfirmRemoveSelfBucketAccess` | `String` | Header, Required | - |
| `body` | [`BucketPolicyRequest`](../../doc/models/bucket-policy-request.md) | Body, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String policy = "policy4";
String contentMD5 = "{{contentMD5}}";
String xAmzConfirmRemoveSelfBucketAccess = "ConfirmRemoveSelfBucketAccess";
BucketPolicyRequest body = new BucketPolicyRequest.Builder(
    "2012-10-17",
    "S3-Console-Auto-Gen-Policy-1573968487385",
    Arrays.asList(
        new Statement.Builder(
            "S3PolicyStmt-DO-NOT-MODIFY-1573968487385",
            "Allow",
            new Principal.Builder(
                "s3.amazonaws.com"
            )
            .build(),
            "s3:PutObject",
            "arn:aws:s3:::working-demo-2/*",
            new Condition.Builder(
                new StringEquals.Builder(
                    "879370021840",
                    "bucket-owner-full-control"
                )
                .build(),
                new ArnLike.Builder(
                    "arn:aws:s3:::working-demo-2"
                )
                .build()
            )
            .build()
        )
        .build()
    )
)
.build();

String bucket = "bucket2";

policyController.bucketPolicy1Async(policy, contentMD5, xAmzConfirmRemoveSelfBucketAccess, body, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```


# Bucket Policy Status

Retrieves the policy status for an Amazon S3 bucket, indicating whether the bucket is public. In order to use this operation, you must have the s3:GetBucketPolicyStatus permission. For more information about Amazon S3 permissions, see Specifying Permissions in a Policy.

```java
CompletableFuture<String> bucketPolicyStatusAsync(
    final String policyStatus,
    final String xAmzContentSha256,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `policyStatus` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`String`

## Example Usage

```java
String policyStatus = "policyStatus6";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";

policyController.bucketPolicyStatusAsync(policyStatus, xAmzContentSha256, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response

```
"<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<PolicyStatus xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><IsPublic>false</IsPublic></PolicyStatus>"
```


# Delete Bucket Policy

This implementation of the DELETE operation uses the policysubresource to delete the policy of a specified bucket. If you are using an identity other than the root user of the AWS account that owns the bucket, the calling identity must have the DeleteBucketPolicy permissions on the specified bucket and belong to the bucket owner's account in order to use this operation.

```java
CompletableFuture<DynamicResponse> deleteBucketPolicyAsync(
    final String policy,
    final String bucket)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `policy` | `String` | Query, Required | - |
| `bucket` | `String` | Template, Required | - |

## Response Type

`DynamicResponse`

## Example Usage

```java
String policy = "policy4";
String bucket = "bucket2";

policyController.deleteBucketPolicyAsync(policy, bucket).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

