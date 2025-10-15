# UpdateContactByExternalIdRequest

## Example Usage

```typescript
import { UpdateContactByExternalIdRequest } from "@postivo/postivo-client/models/operations";

let value: UpdateContactByExternalIdRequest = {
  extId: "my-id-2",
  contact: {
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
  },
};
```

## Fields

| Field                                          | Type                                           | Required                                       | Description                                    | Example                                        |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| `extId`                                        | *string*                                       | :heavy_check_mark:                             | External (custom) ID of the contact to update. | my-id-2                                        |
| `contact`                                      | [models.Contact](../../models/contact.md)      | :heavy_check_mark:                             | A `Contact` object with the updated fields.    |                                                |