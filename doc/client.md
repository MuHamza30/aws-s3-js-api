
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | `Environment` | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| httpClientConfig | [`Consumer<HttpClientConfiguration.Builder>`](../doc/http-client-configuration-builder.md) | Set up Http Client Configuration instance. |

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

## AWS S3Client Class

The gateway for the SDK. This class acts as a factory for the Controllers and also holds the configuration of the SDK.

### Controllers

| Name | Description | Return Type |
|  --- | --- | --- |
| `getAccelerateController()` | Provides access to Accelerate controller. | `AccelerateController` |
| `getACLController()` | Provides access to ACL controller. | `ACLController` |
| `getAnalyticsController()` | Provides access to Analytics controller. | `AnalyticsController` |
| `getCORSController()` | Provides access to CORS controller. | `CORSController` |
| `getEncryptionController()` | Provides access to Encryption controller. | `EncryptionController` |
| `getInventoryController()` | Provides access to Inventory controller. | `InventoryController` |
| `getLifecycleController()` | Provides access to Lifecycle controller. | `LifecycleController` |
| `getLocationController()` | Provides access to Location controller. | `LocationController` |
| `getLoggingController()` | Provides access to Logging controller. | `LoggingController` |
| `getMetricsController()` | Provides access to Metrics controller. | `MetricsController` |
| `getNotificationsController()` | Provides access to Notifications controller. | `NotificationsController` |
| `getPaymentsController()` | Provides access to Payments controller. | `PaymentsController` |
| `getPolicyController()` | Provides access to Policy controller. | `PolicyController` |
| `getReplicationController()` | Provides access to Replication controller. | `ReplicationController` |
| `getTaggingController()` | Provides access to Tagging controller. | `TaggingController` |
| `getVersioningController()` | Provides access to Versioning controller. | `VersioningController` |
| `getWebsiteController()` | Provides access to Website controller. | `WebsiteController` |
| `getBucketsController()` | Provides access to Buckets controller. | `BucketsController` |
| `getLegalHoldController()` | Provides access to LegalHold controller. | `LegalHoldController` |
| `getLockController()` | Provides access to Lock controller. | `LockController` |
| `getRetentionController()` | Provides access to Retention controller. | `RetentionController` |
| `getTorrentController()` | Provides access to Torrent controller. | `TorrentController` |
| `getUploadsController()` | Provides access to Uploads controller. | `UploadsController` |
| `getVersionsController()` | Provides access to Versions controller. | `VersionsController` |
| `getObjectsController()` | Provides access to Objects controller. | `ObjectsController` |
| `getPublicAccessBlockController()` | Provides access to PublicAccessBlock controller. | `PublicAccessBlockController` |
| `getMiscController()` | Provides access to Misc controller. | `MiscController` |

### Methods

| Name | Description | Return Type |
|  --- | --- | --- |
| `shutdown()` | Shutdown the underlying HttpClient instance. | `void` |
| `getEnvironment()` | Current API environment. | `Environment` |
| `getHttpClient()` | The HTTP Client instance to use for making HTTP requests. | `HttpClient` |
| `getHttpClientConfig()` | Http Client Configuration instance. | [`ReadonlyHttpClientConfiguration`](../doc/http-client-configuration.md) |
| `getBaseUri(Server server)` | Get base URI by current environment | `String` |
| `getBaseUri()` | Get base URI by current environment | `String` |

