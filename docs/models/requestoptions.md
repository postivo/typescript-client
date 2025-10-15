# RequestOptions

Additional shipment settings.

## Example Usage

```typescript
import { RequestOptions } from "@postivo/postivo-client/models";
import { RFCDate } from "@postivo/postivo-client/types";

let value: RequestOptions = {
  predefinedConfigId: 32,
  inlineConfig: {
    carrierId: 1,
    serviceId: 1,
    paperId: 1,
    colorPrint: true,
    duplexPrint: true,
    envelopeId: 4453,
    envelopeColorPrint: true,
  },
  senderId: 567,
  dispatchDate: new RFCDate("2025-12-24"),
  callback: null,
  miscInfo: {
    mpk: "dział handlowy",
    orderName: "Wysyłka zaproszeń",
  },
  rotateDocuments: false,
};
```

## Fields

| Field                                                                                              | Type                                                                                               | Required                                                                                           | Description                                                                                        | Example                                                                                            |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `predefinedConfigId`                                                                               | *number*                                                                                           | :heavy_minus_sign:                                                                                 | ID of the shipment configuration profile stored in the user account.                               | 32                                                                                                 |
| `inlineConfig`                                                                                     | *models.InlineConfigUnion*                                                                         | :heavy_minus_sign:                                                                                 | N/A                                                                                                |                                                                                                    |
| `senderId`                                                                                         | *number*                                                                                           | :heavy_minus_sign:                                                                                 | ID of the sender stored in the user account.                                                       | 567                                                                                                |
| `dispatchDate`                                                                                     | [RFCDate](../types/rfcdate.md)                                                                     | :heavy_minus_sign:                                                                                 | Scheduled dispatch date (ISO 8601).                                                                | 2025-12-24                                                                                         |
| `callback`                                                                                         | *models.CallbackUnion*                                                                             | :heavy_minus_sign:                                                                                 | N/A                                                                                                |                                                                                                    |
| `miscInfo`                                                                                         | *models.MiscInfoUnion*                                                                             | :heavy_minus_sign:                                                                                 | N/A                                                                                                |                                                                                                    |
| `rotateDocuments`                                                                                  | *boolean*                                                                                          | :heavy_minus_sign:                                                                                 | If true, rotate all documents 180° before printing (barcodes will be printed on opposite margins). | false                                                                                              |