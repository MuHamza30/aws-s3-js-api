
# Access Control Policy

## Structure

`AccessControlPolicy`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `owner` | [`Owner`](../../doc/models/owner.md) | Required | - |
| `accessControlList` | [`AccessControlList`](../../doc/models/access-control-list.md) | Required | - |

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

