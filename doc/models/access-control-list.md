
# Access Control List

## Structure

`AccessControlList`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `grant` | [`Grant[]`](../../doc/models/grant.md) | Required | - |

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

