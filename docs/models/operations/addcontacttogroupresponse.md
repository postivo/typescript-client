# AddContactToGroupResponse

## Example Usage

```typescript
import { AddContactToGroupResponse } from "@postivo/postivo-client/models/operations";

let value: AddContactToGroupResponse = {
  headers: {},
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

| Field                                                 | Type                                                  | Required                                              | Description                                           |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| `headers`                                             | Record<string, *string*[]>                            | :heavy_check_mark:                                    | N/A                                                   |
| `result`                                              | [models.ErrorResponse](../../models/errorresponse.md) | :heavy_check_mark:                                    | N/A                                                   |