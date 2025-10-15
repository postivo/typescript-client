# ListSendersResponse


## Supported Types

### `models.SenderDetails[]`

```typescript
const value: models.SenderDetails[] = [
  {
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

