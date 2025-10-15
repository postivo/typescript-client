# GetDocumentsResponseResult


## Supported Types

### `models.DocumentResponse`

```typescript
const value: models.DocumentResponse = {
  mimeType: "application/pdf",
  fileStream: "<file content in base64 format>",
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

