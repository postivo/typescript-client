# PredefinedConfig

Predefined configuration usable for dispatching shipments (referenced via `predefined_config_id`).

## Example Usage

```typescript
import { PredefinedConfig } from "@postivo/postivo-client/models";

let value: PredefinedConfig = {
  id: 334,
  name: "Konfiguracja z listem poleconym w kolorze",
  paperName: "A4 (80 g/m2) biały - klasa A",
  colorPrint: true,
  duplexPrint: true,
  envelopeName: "C6/5 (DL)",
  envelopeSize: "229x114",
  envelopeGroupName: "Koperty z logo",
  envelopeColorPrint: true,
};
```

## Fields

| Field                                                        | Type                                                         | Required                                                     | Description                                                  | Example                                                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `id`                                                         | *number*                                                     | :heavy_minus_sign:                                           | Unique predefined configuration ID.                          | 334                                                          |
| `name`                                                       | *string*                                                     | :heavy_minus_sign:                                           | Predefined configuration name.                               | Konfiguracja z listem poleconym w kolorze                    |
| `paperName`                                                  | *string*                                                     | :heavy_minus_sign:                                           | Paper type name.                                             | A4 (80 g/m2) biały - klasa A                                 |
| `colorPrint`                                                 | *boolean*                                                    | :heavy_minus_sign:                                           | Print documents in color (`true`) or grayscale (`false`).    | true                                                         |
| `duplexPrint`                                                | *boolean*                                                    | :heavy_minus_sign:                                           | Print documents duplex (`true`) or single-sided (`false`).   | true                                                         |
| `envelopeName`                                               | *string*                                                     | :heavy_minus_sign:                                           | Preferred envelope type name.                                | C6/5 (DL)                                                    |
| `envelopeSize`                                               | *string*                                                     | :heavy_minus_sign:                                           | Preferred envelope size.                                     | 229x114                                                      |
| `envelopeGroupName`                                          | *string*                                                     | :heavy_minus_sign:                                           | Envelope group name.                                         | Koperty z logo                                               |
| `envelopeColorPrint`                                         | *boolean*                                                    | :heavy_minus_sign:                                           | Print the envelope in color (`true`) or grayscale (`false`). | true                                                         |