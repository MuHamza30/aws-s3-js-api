
# Access Control List

## Structure

`AccessControlList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Grant` | [`List<Grant>`](../../doc/models/grant.md) | Required | - | List<Grant> getGrant() | setGrant(List<Grant> grant) |

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

