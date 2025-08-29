
# Grant 1

## Structure

`Grant1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Grantee` | [`Grantee1`](../../doc/models/grantee-1.md) | Required | - | Grantee1 getGrantee() | setGrantee(Grantee1 grantee) |
| `Permission` | `String` | Required | - | String getPermission() | setPermission(String permission) |

## Example (as XML)

```xml
<Grant>
  <Grantee xsi:type="type0" xmlns:xsi="http://s3.amazonaws.com/doc/2006-03-01/">
    <ID>ID4</ID>
    <DisplayName>DisplayName4</DisplayName>
  </Grantee>
  <Permission>Permission4</Permission>
</Grant>
```

