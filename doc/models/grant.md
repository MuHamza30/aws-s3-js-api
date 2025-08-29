
# Grant

## Structure

`Grant`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Grantee` | [`Grantee`](../../doc/models/grantee.md) | Required | - | Grantee getGrantee() | setGrantee(Grantee grantee) |
| `Permission` | `String` | Required | - | String getPermission() | setPermission(String permission) |

## Example (as XML)

```xml
<Grant>
  <Grantee xsi:type="type0" xmlns:xsi="http://s3.amazonaws.com/doc/2006-03-01/">
    <ID>ID4</ID>
    <DisplayName>DisplayName4</DisplayName>
  </Grantee>
  <Permission>Permission2</Permission>
</Grant>
```

