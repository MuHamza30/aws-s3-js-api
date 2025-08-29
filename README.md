
# Getting Started with AWS S3

## Install the Package

Install the SDK by adding the following dependency in your project's pom.xml file:

```xml
<dependency>
  <groupId>io.sdks</groupId>
  <artifactId>apimatic-aws-s3-api</artifactId>
  <version>1.0.0</version>
</dependency>
```

You can also view the package at:
https://central.sonatype.com/artifact/io.sdks/apimatic-aws-s3-api/1.0.0

## Test the SDK

The generated code and the server can be tested using automatically generated test cases.
JUnit is used as the testing framework and test runner.

In Eclipse, for running the tests do the following:

1. Select the project AWSS3Lib from the package explorer.
2. Select `Run -> Run as -> JUnit Test` or use `Alt + Shift + X` followed by `T` to run the Tests.

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | `Environment` | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| httpClientConfig | [`Consumer<HttpClientConfiguration.Builder>`](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/http-client-configuration-builder.md) | Set up Http Client Configuration instance. |

The API client can be initialized as follows:

```java
import com.amazonaws.s3.AWSS3Client;
import com.amazonaws.s3.Environment;
import com.amazonaws.s3.exceptions.ApiException;
import java.io.IOException;
import javax.xml.bind.JAXBException;

public class Program {
    public static void main(String[] args) {
        AWSS3Client client = new AWSS3Client.Builder()
            .httpClientConfig(configBuilder -> configBuilder
                    .timeout(0))
            .environment(Environment.PRODUCTION)
            .build();

    }
}
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

* [Configuration Interface](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/configuration-interface.md)
* [HttpClientConfiguration](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/http-client-configuration.md)
* [HttpClientConfiguration.Builder](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/http-client-configuration-builder.md)
* [HttpProxyConfiguration](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/http-proxy-configuration.md)
* [HttpProxyConfiguration.Builder](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/http-proxy-configuration-builder.md)

### HTTP

* [Headers](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/headers.md)
* [HttpCallback Interface](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/http-callback-interface.md)
* [HttpContext](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/http-context.md)
* [HttpBodyRequest](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/http-body-request.md)
* [HttpRequest](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/http-request.md)
* [HttpResponse](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/http-response.md)
* [HttpStringResponse](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/http-string-response.md)

### Utilities

* [ApiException](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/api-exception.md)
* [ApiHelper](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/api-helper.md)
* [FileWrapper](https://www.github.com/MuHamza30/aws-s3-js-api/tree/1.0.0/doc/file-wrapper.md)

