# Recipients2

Recipient data for a single shipment. For one recipient, provide a `RecipientInline`, `RecipientFromAddressBook`, or `RecipientFromAddressBookByExternalId` object. For multiple recipients, provide an array of these objects (1–50).


## Supported Types

### `models.RecipientInline`

```typescript
const value: models.RecipientInline = {
  name: "Jan Nowak",
  name2: "Firma Testowa Sp. z o.o.",
  address: "ul. Aleje Jerozolimskie",
  homeNumber: "31",
  flatNumber: "2",
  postCode: "00-999",
  city: "Warszawa",
  phoneNumber: "+48999999999",
  postscript: "Do rąk własnych",
  customId: "my-id-1113",
};
```

### `models.RecipientFromAddressBook`

```typescript
const value: models.RecipientFromAddressBook = {
  id: 344,
  customId: "my-id-1113",
  postscript: "Do rąk własnych",
};
```

### `models.RecipientFromAddressBookByExternalId`

```typescript
const value: models.RecipientFromAddressBookByExternalId = {
  extId: "marcin-344",
  fromShared: true,
  customId: "my-id-1113",
  postscript: "Do rąk własnych",
};
```

### `models.Recipients1[]`

```typescript
const value: models.Recipients1[] = [
  {
    id: 344,
    customId: "my-id-1113",
    postscript: "Do rąk własnych",
  },
];
```

