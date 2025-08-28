# Policy

```ts
const policyController = new PolicyController(client);
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

```ts
async bucketPolicy(
  policy: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<BucketPolicy>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `policy` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`BucketPolicy`](../../doc/models/bucket-policy.md).

## Example Usage

```ts
const policy = 'policy4';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await policyController.bucketPolicy(
    policy,
    xAmzContentSha256,
    bucket
  );
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
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

```ts
async bucketPolicy1(
  policy: string,
  contentMD5: string,
  xAmzConfirmRemoveSelfBucketAccess: string,
  body: BucketPolicyRequest,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `policy` | `string` | Query, Required | - |
| `contentMD5` | `string` | Header, Required | - |
| `xAmzConfirmRemoveSelfBucketAccess` | `string` | Header, Required | - |
| `body` | [`BucketPolicyRequest`](../../doc/models/bucket-policy-request.md) | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const policy = 'policy4';

const contentMD5 = '{{contentMD5}}';

const xAmzConfirmRemoveSelfBucketAccess = 'ConfirmRemoveSelfBucketAccess';

const body: BucketPolicyRequest = {
  version: '2012-10-17',
  id: 'S3-Console-Auto-Gen-Policy-1573968487385',
  statement: [
    {
      sid: 'S3PolicyStmt-DO-NOT-MODIFY-1573968487385',
      effect: 'Allow',
      principal: {
        service: 's3.amazonaws.com',
      },
      action: 's3:PutObject',
      resource: 'arn:aws:s3:::working-demo-2/*',
      condition: {
        stringEquals: {
          awsSourceAccount: '879370021840',
          s3XAmzAcl: 'bucket-owner-full-control',
        },
        arnLike: {
          awsSourceArn: 'arn:aws:s3:::working-demo-2',
        },
      },
    }
  ],
};

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await policyController.bucketPolicy1(
    policy,
    contentMD5,
    xAmzConfirmRemoveSelfBucketAccess,
    body,
    bucket
  );
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```


# Bucket Policy Status

Retrieves the policy status for an Amazon S3 bucket, indicating whether the bucket is public. In order to use this operation, you must have the s3:GetBucketPolicyStatus permission. For more information about Amazon S3 permissions, see Specifying Permissions in a Policy.

```ts
async bucketPolicyStatus(
  policyStatus: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `policyStatus` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `string`.

## Example Usage

```ts
const policyStatus = 'policyStatus6';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await policyController.bucketPolicyStatus(
    policyStatus,
    xAmzContentSha256,
    bucket
  );
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Example Response

```
"<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<PolicyStatus xmlns=\"http://s3.amazonaws.com/doc/2006-03-01/\"><IsPublic>false</IsPublic></PolicyStatus>"
```


# Delete Bucket Policy

This implementation of the DELETE operation uses the policysubresource to delete the policy of a specified bucket. If you are using an identity other than the root user of the AWS account that owns the bucket, the calling identity must have the DeleteBucketPolicy permissions on the specified bucket and belong to the bucket owner's account in order to use this operation.

```ts
async deleteBucketPolicy(
  policy: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `policy` | `string` | Query, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const policy = 'policy4';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await policyController.deleteBucketPolicy(
    policy,
    bucket
  );
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

