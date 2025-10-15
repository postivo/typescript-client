# GetDocumentsRequest

## Example Usage

```typescript
import { GetDocumentsRequest } from "@postivo/postivo-client/models/operations";

let value: GetDocumentsRequest = {
  id: "A0043456",
  type: "dispatch_cert",
};
```

## Fields

| Field                                                                    | Type                                                                     | Required                                                                 | Description                                                              | Example                                                                  |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `id`                                                                     | *string*                                                                 | :heavy_check_mark:                                                       | Single shipment ID assigned by the system when the shipment was created. | A0043456                                                                 |
| `type`                                                                   | [operations.DocumentType](../../models/operations/documenttype.md)       | :heavy_check_mark:                                                       | Type of document/certificate to generate.                                | dispatch_cert                                                            |