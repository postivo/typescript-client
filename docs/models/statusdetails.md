# StatusDetails

Details of a single shipment and its status events

## Example Usage

```typescript
import { StatusDetails } from "@postivo/postivo-client/models";
import { RFCDate } from "@postivo/postivo-client/types";

let value: StatusDetails = {
  shipmentDetails: {
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
  },
  statusEvents: [
    {
      uniqueId: 778656,
      type: "OK",
      code: "ACCEPTED",
      name: "Przesyłka przyjęta do realizacji",
      details: "Przyjęcie do Punktu Dystrybucyjnego",
      date: new Date("2024-06-01T12:00:00Z"),
    },
  ],
};
```

## Fields

| Field                                                  | Type                                                   | Required                                               | Description                                            |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| `shipmentDetails`                                      | [models.ShipmentDetails](../models/shipmentdetails.md) | :heavy_minus_sign:                                     | Single shipment details                                |
| `statusEvents`                                         | [models.StatusEvent](../models/statusevent.md)[]       | :heavy_minus_sign:                                     | List of status events for the shipment.                |