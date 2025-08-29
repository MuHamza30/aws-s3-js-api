
# Access Control Policy 1

## Structure

`AccessControlPolicy1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Owner` | [`Owner`](../../doc/models/owner.md) | Required | - | Owner getOwner() | setOwner(Owner owner) |
| `AccessControlList` | [`AccessControlList1`](../../doc/models/access-control-list-1.md) | Required | - | AccessControlList1 getAccessControlList() | setAccessControlList(AccessControlList1 accessControlList) |

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

