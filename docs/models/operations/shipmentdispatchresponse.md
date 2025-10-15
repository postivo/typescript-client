# ShipmentDispatchResponse

## Example Usage

```typescript
import { ShipmentDispatchResponse } from "@postivo/postivo-client/models/operations";

let value: ShipmentDispatchResponse = {
  headers: {
    "key": [
      "<value 1>",
      "<value 2>",
    ],
    "key1": [
      "<value 1>",
      "<value 2>",
      "<value 3>",
    ],
  },
  result: [],
};
```

## Fields

| Field                                       | Type                                        | Required                                    | Description                                 |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| `headers`                                   | Record<string, *string*[]>                  | :heavy_check_mark:                          | N/A                                         |
| `result`                                    | *operations.ShipmentDispatchResponseResult* | :heavy_check_mark:                          | N/A                                         |