# AddGroupResponseResult


## Supported Types

### `models.GroupResponse`

```typescript
const value: models.GroupResponse = {
  name: "my-group",
  description: "This is a group for school contacts",
  id: 234,
  inherited: false,
};
```

### `models.ErrorResponse`

```typescript
const value: models.ErrorResponse = {
  type: "https://problems-registry.smartbear.com/invalid-body-property-format",
  status: 400,
  title: "Invalid Body property format",
  detail: "The request body contains a malformed property",
  code: "400-21",
  instance: "/rest/messages/sms",
};
```

