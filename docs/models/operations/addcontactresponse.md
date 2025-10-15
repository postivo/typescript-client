# AddContactResponse

## Example Usage

```typescript
import { AddContactResponse } from "@postivo/postivo-client/models/operations";

let value: AddContactResponse = {
  headers: {
    "key": [
      "<value 1>",
    ],
    "key1": [],
  },
  result: {
    type:
      "https://problems-registry.smartbear.com/invalid-body-property-format",
    status: 400,
    title: "Invalid Body property format",
    detail: "The request body contains a malformed property",
    code: "400-21",
    instance: "/rest/messages/sms",
  },
};
```

## Fields

| Field                                 | Type                                  | Required                              | Description                           |
| ------------------------------------- | ------------------------------------- | ------------------------------------- | ------------------------------------- |
| `headers`                             | Record<string, *string*[]>            | :heavy_check_mark:                    | N/A                                   |
| `result`                              | *operations.AddContactResponseResult* | :heavy_check_mark:                    | N/A                                   |