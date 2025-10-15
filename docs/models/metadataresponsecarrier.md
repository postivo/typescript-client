# MetadataResponseCarrier

## Example Usage

```typescript
import { MetadataResponseCarrier } from "@postivo/postivo-client/models";

let value: MetadataResponseCarrier = {
  carrierId: 1,
  carrierName: "Poczta Polska S.A.",
  services: [
    {
      serviceId: 1,
      serviceName: "List zwykły ekonomiczny D+4",
      serviceReturnFee: 4.99,
    },
  ],
};
```

## Fields

| Field                                                                    | Type                                                                     | Required                                                                 | Description                                                              | Example                                                                  |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `carrierId`                                                              | *number*                                                                 | :heavy_minus_sign:                                                       | Unique carrier identifier.                                               | 1                                                                        |
| `carrierName`                                                            | *string*                                                                 | :heavy_minus_sign:                                                       | Carrier display name.                                                    | Poczta Polska S.A.                                                       |
| `services`                                                               | [models.MetadataResponseService](../models/metadataresponseservice.md)[] | :heavy_minus_sign:                                                       | Services (dispatch types) available for this carrier.                    |                                                                          |