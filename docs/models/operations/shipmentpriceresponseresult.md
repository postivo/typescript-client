# ShipmentPriceResponseResult


## Supported Types

### `models.ShipmentPrice[]`

```typescript
const value: models.ShipmentPrice[] = [
  {
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
  },
];
```

### `models.ErrorResponse`

```typescript
const value: models.ErrorResponse = {
  type: "https://problems-registry.smartbear.com/invalid-body-property-format",
  status: 400,
  title: "Invalid Body property format",
  detail: "The request body contains a malformed property",
  code: "400-21",
  instance: "/rest/messages/sms",
};
```

