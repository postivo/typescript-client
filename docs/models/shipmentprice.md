# ShipmentPrice

Pricing details for a single shipment

## Example Usage

```typescript
import { ShipmentPrice } from "@postivo/postivo-client/models";

let value: ShipmentPrice = {
  recipient: {
    name: "Jan Nowak",
    name2: "Firma Testowa Sp. z o.o.",
    address: "ul. Aleje Jerozolimskie",
    homeNumber: "31",
    flatNumber: "2",
    postCode: "00-999",
    city: "Warszawa",
    phoneNumber: "+48999999999",
    postscript: "Do rąk własnych",
  },
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
  status: {
    error: false,
    code: "SENT",
    description: "Przekazano do wysyłki",
    date: new Date("2024-06-01T16:22:07Z"),
  },
  carrier: {
    id: 1,
    name: "Poczta Polska S.A.",
  },
  service: {
    id: 1,
    name: "List zwykły ekonomiczny",
  },
  pageNumber: 3,
  price: 4.16,
};
```

## Fields

| Field                                                            | Type                                                             | Required                                                         | Description                                                      | Example                                                          |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| `recipient`                                                      | [models.Recipient](../models/recipient.md)                       | :heavy_minus_sign:                                               | Recipient data for a shipment, including full postal address.    |                                                                  |
| `sender`                                                         | [models.Sender](../models/sender.md)                             | :heavy_minus_sign:                                               | Sender data for the shipment.                                    |                                                                  |
| `status`                                                         | [models.ShipmentPriceStatus](../models/shipmentpricestatus.md)   | :heavy_minus_sign:                                               | Shipment processing status.                                      |                                                                  |
| `carrier`                                                        | [models.ShipmentPriceCarrier](../models/shipmentpricecarrier.md) | :heavy_minus_sign:                                               | Postal operator that will handle the shipment.                   |                                                                  |
| `service`                                                        | [models.ShipmentPriceService](../models/shipmentpriceservice.md) | :heavy_minus_sign:                                               | Service (shipment type) selected.                                |                                                                  |
| `pageNumber`                                                     | *number*                                                         | :heavy_minus_sign:                                               | Total number of pages across all documents in the shipment.      | 3                                                                |
| `price`                                                          | *number*                                                         | :heavy_minus_sign:                                               | Shipment price (PLN).                                            | 4.16                                                             |