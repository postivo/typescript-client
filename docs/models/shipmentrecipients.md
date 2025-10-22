# ShipmentRecipients

Recipient data for a single shipment. For one recipient, provide a `RecipientInline`, `RecipientFromAddressBook`, or `RecipientFromAddressBookByExternalId` object. For multiple recipients, provide an array of these objects (1–50).


## Supported Types

### `models.Recipients`

```typescript
const value: models.Recipients = {
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
  customId: "my-id-1113",
};
```

### `models.Recipients[]`

```typescript
const value: models.Recipients[] = [
  {
    extId: "marcin-344",
    inherited: true,
    customId: "my-id-1113",
    postscript: "Do rąk własnych",
  },
];
```

