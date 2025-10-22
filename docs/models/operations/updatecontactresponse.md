# UpdateContactResponse

## Example Usage

```typescript
import { UpdateContactResponse } from "@postivo/postivo-client/models/operations";

let value: UpdateContactResponse = {
  headers: {
    "key": [],
  },
  result: {
    name: "Jan Nowak",
    name2: "Firma Testowa Sp. z o.o.",
    address: "ul. Aleje Jerozolimskie",
    homeNumber: "31",
    flatNumber: "2",
    postCode: "00-999",
    city: "Warszawa",
    country: "PL",
    phoneNumber: "+48999999999",
    extId: "my-contact-1",
    groupIds: [
      13,
      534,
    ],
    id: 776,
    inherited: false,
  },
};
```

## Fields

| Field                                    | Type                                     | Required                                 | Description                              |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| `headers`                                | Record<string, *string*[]>               | :heavy_check_mark:                       | N/A                                      |
| `result`                                 | *operations.UpdateContactResponseResult* | :heavy_check_mark:                       | N/A                                      |