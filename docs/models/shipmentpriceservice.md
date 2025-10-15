# ShipmentPriceService

Service (shipment type) selected.

## Example Usage

```typescript
import { ShipmentPriceService } from "@postivo/postivo-client/models";

let value: ShipmentPriceService = {
  id: 1,
  name: "List zwykły ekonomiczny",
};
```

## Fields

| Field                                     | Type                                      | Required                                  | Description                               | Example                                   |
| ----------------------------------------- | ----------------------------------------- | ----------------------------------------- | ----------------------------------------- | ----------------------------------------- |
| `id`                                      | *number*                                  | :heavy_minus_sign:                        | Service type ID (shipment/letter type).   | 1                                         |
| `name`                                    | *string*                                  | :heavy_minus_sign:                        | Service type name (shipment/letter type). | List zwykły ekonomiczny                   |