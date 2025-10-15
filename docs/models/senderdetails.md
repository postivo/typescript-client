# SenderDetails

Extended sender details.

## Example Usage

```typescript
import { SenderDetails } from "@postivo/postivo-client/models";

let value: SenderDetails = {
  id: 665,
  sender: {
    name: "Jan Nowak",
    name2: "Firma Testowa Sp. z o.o.",
    address: "ul. Aleje Jerozolimskie",
    homeNumber: "31",
    flatNumber: "2",
    postCode: "00-999",
    city: "Warszawa",
    country: "PL",
  },
  active: true,
  default: true,
};
```

## Fields

| Field                                         | Type                                          | Required                                      | Description                                   | Example                                       |
| --------------------------------------------- | --------------------------------------------- | --------------------------------------------- | --------------------------------------------- | --------------------------------------------- |
| `id`                                          | *number*                                      | :heavy_minus_sign:                            | Unique sender ID.                             | 665                                           |
| `sender`                                      | [models.Sender](../models/sender.md)          | :heavy_check_mark:                            | Sender data for the shipment.                 |                                               |
| `active`                                      | *boolean*                                     | :heavy_check_mark:                            | Indicates whether the sender is active.       | true                                          |
| `default`                                     | *boolean*                                     | :heavy_check_mark:                            | Indicates whether this is the default sender. | true                                          |