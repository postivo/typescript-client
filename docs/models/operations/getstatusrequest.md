# GetStatusRequest

## Example Usage

```typescript
import { GetStatusRequest } from "@postivo/postivo-client/models/operations";

let value: GetStatusRequest = {
  ids: [
    "A0043456",
  ],
};
```

## Fields

| Field                                                                                                               | Type                                                                                                                | Required                                                                                                            | Description                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `ids`                                                                                                               | *string*[]                                                                                                          | :heavy_check_mark:                                                                                                  | Shipment IDs assigned by the system (comma-separated). The system accepts a maximum of **50** identifiers per call. |