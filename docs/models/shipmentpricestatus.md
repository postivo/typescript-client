# ShipmentPriceStatus

Shipment processing status.

## Example Usage

```typescript
import { ShipmentPriceStatus } from "@postivo/postivo-client/models";

let value: ShipmentPriceStatus = {
  error: false,
  code: "SENT",
  description: "Przekazano do wysyłki",
  date: new Date("2024-06-01T16:22:07Z"),
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   | Example                                                                                       |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `error`                                                                                       | *boolean*                                                                                     | :heavy_minus_sign:                                                                            | Indicates whether an error occurred during processing.                                        | false                                                                                         |
| `code`                                                                                        | *string*                                                                                      | :heavy_minus_sign:                                                                            | Status code.                                                                                  | SENT                                                                                          |
| `description`                                                                                 | *string*                                                                                      | :heavy_minus_sign:                                                                            | Status description.                                                                           | Przekazano do wysyłki                                                                         |
| `date`                                                                                        | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_minus_sign:                                                                            | Status timestamp (UTC).                                                                       | 2024-06-01T16:22:07Z                                                                          |