# ShipmentPriceResponse

## Example Usage

```typescript
import { ShipmentPriceResponse } from "@postivo/postivo-client/models/operations";

let value: ShipmentPriceResponse = {
  headers: {
    "key": [
      "<value 1>",
      "<value 2>",
    ],
    "key1": [
      "<value 1>",
      "<value 2>",
    ],
    "key2": [
      "<value 1>",
      "<value 2>",
    ],
  },
  result: [
    {
      recipient: {
        name: "Jan Nowak",
        name2: "Firma Testowa Sp. z o.o.",
        address: "ul. Aleje Jerozolimskie",
        homeNumber: "31",
        flatNumber: "2",
        postCode: "00-999",
        city: "Warszawa",
        country: "PL",
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
    },
  ],
};
```

## Fields

| Field                                    | Type                                     | Required                                 | Description                              |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| `headers`                                | Record<string, *string*[]>               | :heavy_check_mark:                       | N/A                                      |
| `result`                                 | *operations.ShipmentPriceResponseResult* | :heavy_check_mark:                       | N/A                                      |