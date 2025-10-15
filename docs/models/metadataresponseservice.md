# MetadataResponseService

## Example Usage

```typescript
import { MetadataResponseService } from "@postivo/postivo-client/models";

let value: MetadataResponseService = {
  serviceId: 1,
  serviceName: "List zwykły ekonomiczny D+4",
  serviceReturnFee: 4.99,
};
```

## Fields

| Field                                             | Type                                              | Required                                          | Description                                       | Example                                           |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| `serviceId`                                       | *number*                                          | :heavy_minus_sign:                                | Unique service (dispatch type) identifier.        | 1                                                 |
| `serviceName`                                     | *string*                                          | :heavy_minus_sign:                                | Service (dispatch type) name.                     | List zwykły ekonomiczny D+4                       |
| `serviceReturnFee`                                | *number*                                          | :heavy_minus_sign:                                | Return fee charged when the shipment is returned. | 4.99                                              |