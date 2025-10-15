# PingResponse


## Supported Types

### `models.PingResponse`

```typescript
const value: models.PingResponse = {
  status: "OK",
  version: "1.0",
  sandbox: false,
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

