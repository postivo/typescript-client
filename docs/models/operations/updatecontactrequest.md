# UpdateContactRequest

## Example Usage

```typescript
import { UpdateContactRequest } from "@postivo/postivo-client/models/operations";

let value: UpdateContactRequest = {
  id: 14,
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

| Field                                       | Type                                        | Required                                    | Description                                 | Example                                     |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| `id`                                        | *number*                                    | :heavy_check_mark:                          | ID of the contact to update.                | 14                                          |
| `contact`                                   | [models.Contact](../../models/contact.md)   | :heavy_check_mark:                          | A `Contact` object with the updated fields. |                                             |