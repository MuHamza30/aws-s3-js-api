
# Grant

## Structure

`Grant`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `grantee` | [`Grantee`](../../doc/models/grantee.md) | Required | - |
| `permission` | `string` | Required | - |

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

