# ShipmentDetails

Single shipment details

## Example Usage

```typescript
import { ShipmentDetails } from "@postivo/postivo-client/models";
import { RFCDate } from "@postivo/postivo-client/types";

let value: ShipmentDetails = {
  id: "A00323234",
  customId: "custom-id-A44445T",
  trackingNumber: "0032322323243443",
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
    name: "Przekazano do wysyłki",
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
  dispatchDate: new RFCDate("2024-06-01"),
  pageNumber: 3,
  price: 4.16,
};
```

## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          | Example                                                              |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `id`                                                                 | *string*                                                             | :heavy_minus_sign:                                                   | Unique shipment identifier.                                          | A00323234                                                            |
| `customId`                                                           | *string*                                                             | :heavy_minus_sign:                                                   | Custom shipment ID assigned by the user.                             | custom-id-A44445T                                                    |
| `trackingNumber`                                                     | *string*                                                             | :heavy_minus_sign:                                                   | Carrier-provided shipment tracking number.                           | 0032322323243443                                                     |
| `recipient`                                                          | [models.Recipient](../models/recipient.md)                           | :heavy_minus_sign:                                                   | Recipient data for a shipment, including full postal address.        |                                                                      |
| `sender`                                                             | [models.Sender](../models/sender.md)                                 | :heavy_minus_sign:                                                   | Sender data for the shipment.                                        |                                                                      |
| `status`                                                             | [models.ShipmentDetailsStatus](../models/shipmentdetailsstatus.md)   | :heavy_minus_sign:                                                   | Shipment processing status.                                          |                                                                      |
| `carrier`                                                            | [models.ShipmentDetailsCarrier](../models/shipmentdetailscarrier.md) | :heavy_minus_sign:                                                   | Postal operator handling the shipment.                               |                                                                      |
| `service`                                                            | [models.ShipmentDetailsService](../models/shipmentdetailsservice.md) | :heavy_minus_sign:                                                   | Service (shipment type) used.                                        |                                                                      |
| `dispatchDate`                                                       | [RFCDate](../types/rfcdate.md)                                       | :heavy_minus_sign:                                                   | Dispatch date.                                                       | 2024-06-01                                                           |
| `pageNumber`                                                         | *number*                                                             | :heavy_minus_sign:                                                   | Total number of pages across all documents in the shipment.          | 3                                                                    |
| `price`                                                              | *number*                                                             | :heavy_minus_sign:                                                   | Shipment price (PLN).                                                | 4.16                                                                 |