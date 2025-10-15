# ShipmentCancellation

Result of cancelling a single shipment

## Example Usage

```typescript
import { ShipmentCancellation } from "@postivo/postivo-client/models";

let value: ShipmentCancellation = {
  id: "A0043456",
  status: 400,
  error: {
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

| Field                                                                                | Type                                                                                 | Required                                                                             | Description                                                                          | Example                                                                              |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `id`                                                                                 | *string*                                                                             | :heavy_minus_sign:                                                                   | Shipment ID.                                                                         | A0043456                                                                             |
| `status`                                                                             | *number*                                                                             | :heavy_minus_sign:                                                                   | Cancellation status code (`204` if cancelled successfully; otherwise an error code). | 400                                                                                  |
| `error`                                                                              | [models.ErrorResponse](../models/errorresponse.md)                                   | :heavy_minus_sign:                                                                   | Problem Details object (RFC 9457) describing the error.                              |                                                                                      |