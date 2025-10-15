# Envelope

## Example Usage

```typescript
import { Envelope } from "@postivo/postivo-client/models";

let value: Envelope = {
  envelopeId: 42,
  envelopeName: "Koperta C5",
  maxSheets: 10,
};
```

## Fields

| Field                                                     | Type                                                      | Required                                                  | Description                                               | Example                                                   |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| `envelopeId`                                              | *number*                                                  | :heavy_minus_sign:                                        | Unique envelope template identifier.                      | 42                                                        |
| `envelopeName`                                            | *string*                                                  | :heavy_minus_sign:                                        | Envelope template name.                                   | Koperta C5                                                |
| `maxSheets`                                               | *number*                                                  | :heavy_minus_sign:                                        | Maximum number of sheets supported by this envelope type. | 10                                                        |