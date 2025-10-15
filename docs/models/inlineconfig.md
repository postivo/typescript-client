# InlineConfig

Shipment configuration parameters. Overrides settings loaded from `predefined_config_id`.

## Example Usage

```typescript
import { InlineConfig } from "@postivo/postivo-client/models";

let value: InlineConfig = {
  carrierId: 1,
  serviceId: 1,
  paperId: 1,
  colorPrint: true,
  duplexPrint: true,
  envelopeId: 4453,
  envelopeColorPrint: true,
};
```

## Fields

| Field                                                                    | Type                                                                     | Required                                                                 | Description                                                              | Example                                                                  |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `carrierId`                                                              | *number*                                                                 | :heavy_check_mark:                                                       | Preferred carrier identifier.                                            | 1                                                                        |
| `serviceId`                                                              | *number*                                                                 | :heavy_check_mark:                                                       | Preferred service identifier (shipment type).                            | 1                                                                        |
| `paperId`                                                                | *number*                                                                 | :heavy_minus_sign:                                                       | Preferred paper type identifier.                                         | 1                                                                        |
| `colorPrint`                                                             | *boolean*                                                                | :heavy_minus_sign:                                                       | Print documents in color (`true`) or grayscale (`false`).                | true                                                                     |
| `duplexPrint`                                                            | *boolean*                                                                | :heavy_minus_sign:                                                       | Print documents duplex (`true`) or single-sided (`false`).               | true                                                                     |
| `envelopeId`                                                             | *number*                                                                 | :heavy_minus_sign:                                                       | Preferred envelope size/template identifier defined in the user account. | 4453                                                                     |
| `envelopeColorPrint`                                                     | *boolean*                                                                | :heavy_minus_sign:                                                       | Print the envelope in color (`true`) or grayscale (`false`).             | true                                                                     |