
# Access Control List 1

## Structure

`AccessControlList1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Grant` | [`Grant1`](../../doc/models/grant-1.md) | Required | - | Grant1 getGrant() | setGrant(Grant1 grant) |

## Example (as XML)

```xml
<AccessControlList>
  <Grant>
    <Grantee xsi:type="type0" xmlns:xsi="http://s3.amazonaws.com/doc/2006-03-01/">
      <ID>ID4</ID>
      <DisplayName>DisplayName4</DisplayName>
    </Grantee>
    <Permission>Permission2</Permission>
  </Grant>
</AccessControlList>
```

