# Versions

```ts
const versionsController = new VersionsController(client);
```

## Class Name

`VersionsController`


# Object Versions

Returns metadata about all of the versions of objects in a bucket. You can also use request parameters as selection criteria to return metadata about a subset of all the object versions.

```ts
async objectVersions(
  versions: string,
  delimiter: string,
  encodingType: string,
  keyMarker: string,
  maxKeys: string,
  prefix: string,
  versionIdMarker: string,
  xAmzContentSha256: string,
  bucket: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ListVersionsResult>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `versions` | `string` | Query, Required | - |
| `delimiter` | `string` | Query, Required | - |
| `encodingType` | `string` | Query, Required | - |
| `keyMarker` | `string` | Query, Required | - |
| `maxKeys` | `string` | Query, Required | - |
| `prefix` | `string` | Query, Required | - |
| `versionIdMarker` | `string` | Query, Required | - |
| `xAmzContentSha256` | `string` | Header, Required | - |
| `bucket` | `string` | Template, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ListVersionsResult`](../../doc/models/list-versions-result.md).

## Example Usage

```ts
const versions = 'versions0';

const delimiter = '{{Delimiter}}';

const encodingType = '{{EncodingType}}';

const keyMarker = '{{KeyMarker}}';

const maxKeys = '{{MaxKeys}}';

const prefix = '{{Prefix}}';

const versionIdMarker = '{{VersionIdMarker}}';

const xAmzContentSha256 = 'UNSIGNED-PAYLOAD';

const bucket = 'bucket2';

try {
  const { result, ...httpResponse } = await versionsController.objectVersions(
    versions,
    delimiter,
    encodingType,
    keyMarker,
    maxKeys,
    prefix,
    versionIdMarker,
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

