# ACL

```ts
const aCLController = new ACLController(client);
```

## Class Name

`ACLController`

## Methods

* [Bucket ACL](../../doc/controllers/acl.md#bucket-acl)
* [Bucket ACL1](../../doc/controllers/acl.md#bucket-acl1)
* [ACL](../../doc/controllers/acl.md#acl)
* [ACL1](../../doc/controllers/acl.md#acl1)


# Bucket ACL

This implementation of the GET operation uses the acl subresource to return the access control list (ACL) of a bucket. To use GET to return the ACL of the bucket, you must have READ_ACP access to the bucket. If READ_ACP permission is granted to the anonymous user, you can return the ACL of the bucket without using an authorization header.

```ts
async bucketACL(
  acl: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AccessControlPolicy>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `acl` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AccessControlPolicy`](../../doc/models/access-control-policy.md).

## Example Usage

```ts
const acl = 'acl0';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await aCLController.bucketACL(
    acl,
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

## Example Response *(as XML)*

```xml
<AccessControlPolicy>
  <Owner>
    <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
    <DisplayName>kinlane</DisplayName>
  </Owner>
  <AccessControlList>
    <Grant>
      <Grantee xsi:type="CanonicalUser" xmlns:xsi="http://s3.amazonaws.com/doc/2006-03-01/">
        <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
        <DisplayName>kinlane</DisplayName>
      </Grantee>
      <Permission>FULL_CONTROL</Permission>
    </Grant>
    <Grant>
      <Grantee xsi:type="CanonicalUser" xmlns:xsi="http://s3.amazonaws.com/doc/2006-03-01/">
        <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
        <DisplayName>kinlane</DisplayName>
      </Grantee>
      <Permission>FULL_CONTROL</Permission>
    </Grant>
  </AccessControlList>
</AccessControlPolicy>
```


# Bucket ACL1

Sets the permissions on an existing bucket using access control lists (ACL). For more information, see Using ACLs. To set the ACL of a bucket, you must have WRITE_ACP permission.

```ts
async bucketACL1(
  acl: string,
  body: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `acl` | `string` | Query, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const acl = 'acl0';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<AccessControlPolicy xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n    <Owner>\n        <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>\n        <DisplayName>kinlane</DisplayName>\n    </Owner>\n    <AccessControlList>\n        <Grant>\n            <Grantee xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="CanonicalUser">\n                <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>\n                <DisplayName>kinlane</DisplayName>\n            </Grantee>\n            <Permission>FULL_CONTROL</Permission>\n        </Grant>\n        <Grant>\n            <Grantee xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="CanonicalUser">\n                <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>\n                <DisplayName>kinlane</DisplayName>\n            </Grantee>\n            <Permission>FULL_CONTROL</Permission>\n        </Grant>\n    </AccessControlList>\n</AccessControlPolicy>';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await aCLController.bucketACL1(
    acl,
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


# ACL

Returns the access control list (ACL) of an object. To use this operation, you must have READ_ACP access to the object.

```ts
async aCL(
  acl: string,
  bucket: string,
  key: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AccessControlPolicy1>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `acl` | `string` | Query, Required | - |
| `bucket` | `string` | Template, Required | - |
| `key` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AccessControlPolicy1`](../../doc/models/access-control-policy-1.md).

## Example Usage

```ts
const acl = 'acl0';

const bucket = 'bucket2';

const key = 'key0';

try {
  const { result, ...httpResponse } = await aCLController.aCL(
    acl,
    bucket,
    key
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

## Example Response *(as XML)*

```xml
<AccessControlPolicy>
  <Owner>
    <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
    <DisplayName>kinlane</DisplayName>
  </Owner>
  <AccessControlList>
    <Grant>
      <Grantee xsi:type="CanonicalUser" xmlns:xsi="http://s3.amazonaws.com/doc/2006-03-01/">
        <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>
        <DisplayName>kinlane</DisplayName>
      </Grantee>
      <Permission>FULL_CONTROL</Permission>
    </Grant>
  </AccessControlList>
</AccessControlPolicy>
```


# ACL1

Returns the access control list (ACL) of an object. To use this operation, you must have READ_ACP access to the object.

```ts
async aCL1(
  acl: string,
  body: string,
  bucket: string,
  key: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `acl` | `string` | Query, Required | - |
| `body` | `string` | Body, Required | - |
| `bucket` | `string` | Template, Required | - |
| `key` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const acl = 'acl0';

const body = '<?xml version="1.0" encoding="UTF-8"?>\n<AccessControlPolicy xmlns="http://s3.amazonaws.com/doc/2006-03-01/">\n    <Owner>\n        <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>\n        <DisplayName>kinlane</DisplayName>\n    </Owner>\n    <AccessControlList>\n        <Grant>\n            <Grantee xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="CanonicalUser">\n                <ID>94aebaef4c4fbbe84a36f076a1adbf6208742d219ac1cecb29939e262efabf56</ID>\n                <DisplayName>kinlane</DisplayName>\n            </Grantee>\n            <Permission>FULL_CONTROL</Permission>\n        </Grant>\n    </AccessControlList>\n</AccessControlPolicy>';

const bucket = 'bucket2';

const key = 'key0';

try {
  const { result, ...httpResponse } = await aCLController.aCL1(
    acl,
    body,
    bucket,
    key
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

