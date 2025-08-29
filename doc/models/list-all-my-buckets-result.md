
# List All My Buckets Result

## Structure

`ListAllMyBucketsResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Owner` | [`Owner`](../../doc/models/owner.md) | Required | - | Owner getOwner() | setOwner(Owner owner) |
| `Buckets` | [`Buckets`](../../doc/models/buckets.md) | Required | - | Buckets getBuckets() | setBuckets(Buckets buckets) |

## Example (as XML)

```xml
<ListAllMyBucketsResult>
  <Owner>
    <ID>ID4</ID>
    <DisplayName>DisplayName6</DisplayName>
  </Owner>
  <Buckets>
    <Bucket>
      <Name>Name2</Name>
      <CreationDate>CreationDate8</CreationDate>
    </Bucket>
  </Buckets>
</ListAllMyBucketsResult>
```

