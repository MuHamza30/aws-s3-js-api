
# Access Control Policy

## Structure

`AccessControlPolicy`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Owner` | [`Owner`](../../doc/models/owner.md) | Required | - | Owner getOwner() | setOwner(Owner owner) |
| `AccessControlList` | [`AccessControlList`](../../doc/models/access-control-list.md) | Required | - | AccessControlList getAccessControlList() | setAccessControlList(AccessControlList accessControlList) |

## Example (as XML)

```xml
<AccessControlPolicy>
  <Owner>
    <ID>ID4</ID>
    <DisplayName>DisplayName6</DisplayName>
  </Owner>
  <AccessControlList>
    <Grant>
      <Grantee xsi:type="type0" xmlns:xsi="http://s3.amazonaws.com/doc/2006-03-01/">
        <ID>ID4</ID>
        <DisplayName>DisplayName4</DisplayName>
      </Grantee>
      <Permission>Permission2</Permission>
    </Grant>
  </AccessControlList>
</AccessControlPolicy>
```

