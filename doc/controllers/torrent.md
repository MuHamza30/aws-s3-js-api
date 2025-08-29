# Torrent

```java
TorrentController torrentController = client.getTorrentController();
```

## Class Name

`TorrentController`


# Object Torrent

Return torrent files from a bucket. BitTorrent can save you bandwidth when you're distributing large files. For more information about BitTorrent, see Amazon S3 Torrent.

```java
CompletableFuture<Void> objectTorrentAsync(
    final String torrent,
    final String xAmzContentSha256,
    final String bucket,
    final String key)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `torrent` | `String` | Query, Required | - |
| `xAmzContentSha256` | `String` | Header, Required | - |
| `bucket` | `String` | Template, Required | - |
| `key` | `String` | Template, Required | - |

## Response Type

`void`

## Example Usage

```java
String torrent = "torrent4";
String xAmzContentSha256 = "UNSIGNED-PAYLOAD";
String bucket = "bucket2";
String key = "key0";

torrentController.objectTorrentAsync(torrent, xAmzContentSha256, bucket, key).thenAccept(result -> {
    // TODO success callback handler
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

