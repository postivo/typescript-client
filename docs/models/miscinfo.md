# MiscInfo

Additional shipment metadata. At least one of `order_name` or `mpk` must be provided.

## Example Usage

```typescript
import { MiscInfo } from "@postivo/postivo-client/models";

let value: MiscInfo = {
  mpk: "dział handlowy",
  orderName: "Wysyłka zaproszeń",
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   | Example                                                                                       |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `mpk`                                                                                         | *string*                                                                                      | :heavy_minus_sign:                                                                            | MPK (“miejsce powstania kosztu”) — billing cost-center identifier to be included on invoices. | dział handlowy                                                                                |
| `orderName`                                                                                   | *string*                                                                                      | :heavy_minus_sign:                                                                            | Order name assigned to this shipment; displayed in reports and related views.                 | Wysyłka zaproszeń                                                                             |