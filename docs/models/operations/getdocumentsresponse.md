# GetDocumentsResponse

## Example Usage

```typescript
import { GetDocumentsResponse } from "@postivo/postivo-client/models/operations";

let value: GetDocumentsResponse = {
  headers: {
    "key": [],
  },
  result: {
    mimeType: "application/pdf",
    fileStream: "<file content in base64 format>",
  },
};
```

## Fields

| Field                                   | Type                                    | Required                                | Description                             |
| --------------------------------------- | --------------------------------------- | --------------------------------------- | --------------------------------------- |
| `headers`                               | Record<string, *string*[]>              | :heavy_check_mark:                      | N/A                                     |
| `result`                                | *operations.GetDocumentsResponseResult* | :heavy_check_mark:                      | N/A                                     |