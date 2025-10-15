# ShipmentDetailsStatus

Shipment processing status.

## Example Usage

```typescript
import { ShipmentDetailsStatus } from "@postivo/postivo-client/models";

let value: ShipmentDetailsStatus = {
  error: false,
  code: "SENT",
  name: "Przekazano do wysyłki",
  date: new Date("2024-06-01T16:22:07Z"),
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   | Example                                                                                       |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `error`                                                                                       | *boolean*                                                                                     | :heavy_minus_sign:                                                                            | Indicates whether an error occurred during shipment processing.                               | false                                                                                         |
| `code`                                                                                        | *string*                                                                                      | :heavy_minus_sign:                                                                            | Shipment status code.                                                                         | SENT                                                                                          |
| `name`                                                                                        | *string*                                                                                      | :heavy_minus_sign:                                                                            | Shipment status description.                                                                  | Przekazano do wysyłki                                                                         |
| `date`                                                                                        | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_minus_sign:                                                                            | Date and time of the shipment status change (UTC).                                            | 2024-06-01T16:22:07Z                                                                          |