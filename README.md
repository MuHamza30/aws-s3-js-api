
# Getting Started with AWS S3

## Install the Package

Run the following command from your project directory to install the package from npm:

```bash
npm install aws-s3-api@1.0.0
```

For additional package details, see the [Npm page for the aws-s3-api@1.0.0 npm](https://www.npmjs.com/package/aws-s3-api/v/1.0.0).

## Test the SDK

To validate the functionality of this SDK, you can execute all tests located in the `test` directory. This SDK utilizes `Jest` as both the testing framework and test runner.

To run the tests, navigate to the root directory of the SDK and execute the following command:

```bash
npm run test
```

Or you can also run tests with coverage report:

```bash
npm run test:coverage
```

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | `Environment` | The API environment. <br> **Default: `Environment.Production`** |
| timeout | `number` | Timeout for API calls.<br>*Default*: `0` |
| httpClientOptions | [`Partial<HttpClientOptions>`](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/http-client-options.md) | Stable configurable http client options. |
| unstableHttpClientOptions | `any` | Unstable configurable http client options. |

The API client can be initialized as follows:

```ts
import { Client, Environment } from 'aws-s3-api';

const client = new Client({
  timeout: 0,
  environment: Environment.Production,
});
```

## List of APIs

* [Legal Hold](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/legal-hold.md)
* [Public Access Block](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/public-access-block.md)
* [Accelerate](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/accelerate.md)
* [ACL](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/acl.md)
* [Analytics](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/analytics.md)
* [CORS](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/cors.md)
* [Encryption](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/encryption.md)
* [Inventory](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/inventory.md)
* [Lifecycle](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/lifecycle.md)
* [Location](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/location.md)
* [Logging](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/logging.md)
* [Metrics](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/metrics.md)
* [Notifications](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/notifications.md)
* [Payments](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/payments.md)
* [Policy](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/policy.md)
* [Replication](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/replication.md)
* [Tagging](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/tagging.md)
* [Versioning](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/versioning.md)
* [Website](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/website.md)
* [Buckets](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/buckets.md)
* [Lock](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/lock.md)
* [Retention](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/retention.md)
* [Torrent](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/torrent.md)
* [Uploads](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/uploads.md)
* [Versions](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/versions.md)
* [Objects](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/objects.md)
* [Misc](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/controllers/misc.md)

## SDK Infrastructure

### Configuration

* [HttpClientOptions](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/http-client-options.md)
* [RetryConfiguration](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/retry-configuration.md)
* [ProxySettings](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/proxy-settings.md)

### HTTP

* [HttpRequest](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/http-request.md)

### Utilities

* [ApiResponse](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/api-response.md)
* [ApiError](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/api-error.md)

