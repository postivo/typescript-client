# ShipmentDetailsCarrier

Postal operator handling the shipment.

## Example Usage

```typescript
import { ShipmentDetailsCarrier } from "@postivo/postivo-client/models";

let value: ShipmentDetailsCarrier = {
  id: 1,
  name: "Poczta Polska S.A.",
};
```

## Fields

| Field                 | Type                  | Required              | Description           | Example               |
| --------------------- | --------------------- | --------------------- | --------------------- | --------------------- |
| `id`                  | *number*              | :heavy_minus_sign:    | Postal operator ID.   | 1                     |
| `name`                | *string*              | :heavy_minus_sign:    | Postal operator name. | Poczta Polska S.A.    |