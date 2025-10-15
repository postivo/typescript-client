# EnvelopeTemplate

## Example Usage

```typescript
import { EnvelopeTemplate } from "@postivo/postivo-client/models";

let value: EnvelopeTemplate = {
  envelopeGroupName: "Koperty z logiem firmy",
  envelopeGroupDescription: "Koperty z logiem naszej firmy w lewym górnym rogu",
  envelope: [
    {
      envelopeId: 42,
      envelopeName: "Koperta C5",
      maxSheets: 10,
    },
  ],
};
```

## Fields

| Field                                             | Type                                              | Required                                          | Description                                       | Example                                           |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| `envelopeGroupName`                               | *string*                                          | :heavy_minus_sign:                                | Envelope template group name.                     | Koperty z logiem firmy                            |
| `envelopeGroupDescription`                        | *string*                                          | :heavy_minus_sign:                                | Envelope template group description.              | Koperty z logiem naszej firmy w lewym górnym rogu |
| `envelope`                                        | [models.Envelope](../models/envelope.md)[]        | :heavy_minus_sign:                                | Envelope templates in this group.                 |                                                   |