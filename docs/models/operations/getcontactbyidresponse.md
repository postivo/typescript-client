# GetContactByIdResponse


## Supported Types

### `models.ContactResponse`

```typescript
const value: models.ContactResponse = {
  name: "Jan Nowak",
  name2: "Firma Testowa Sp. z o.o.",
  address: "ul. Aleje Jerozolimskie",
  homeNumber: "31",
  flatNumber: "2",
  postCode: "00-999",
  city: "Warszawa",
  phoneNumber: "+48999999999",
  extId: "my-contact-1",
  groupIds: [
    13,
    534,
  ],
  id: 776,
  inherited: false,
};
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

