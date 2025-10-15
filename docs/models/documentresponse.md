# DocumentResponse

Generated document content.

## Example Usage

```typescript
import { DocumentResponse } from "@postivo/postivo-client/models";

let value: DocumentResponse = {
  mimeType: "application/pdf",
  fileStream: "<file content in base64 format>",
};
```

## Fields

| Field                            | Type                             | Required                         | Description                      | Example                          |
| -------------------------------- | -------------------------------- | -------------------------------- | -------------------------------- | -------------------------------- |
| `mimeType`                       | *string*                         | :heavy_check_mark:               | Document MIME type.              | application/pdf                  |
| `fileStream`                     | *string*                         | :heavy_minus_sign:               | Base64-encoded document content. | <file content in base64 format>  |