# AddSenderResponse

## Example Usage

```typescript
import { AddSenderResponse } from "@postivo/postivo-client/models/operations";

let value: AddSenderResponse = {
  headers: {
    "key": [
      "<value 1>",
    ],
  },
  result: {
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
};
```

## Fields

| Field                                | Type                                 | Required                             | Description                          |
| ------------------------------------ | ------------------------------------ | ------------------------------------ | ------------------------------------ |
| `headers`                            | Record<string, *string*[]>           | :heavy_check_mark:                   | N/A                                  |
| `result`                             | *operations.AddSenderResponseResult* | :heavy_check_mark:                   | N/A                                  |