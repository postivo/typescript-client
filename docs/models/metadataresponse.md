# MetadataResponse

Metadata response.

## Example Usage

```typescript
import { MetadataResponse } from "@postivo/postivo-client/models";

let value: MetadataResponse = {
  carriers: [
    {
      carrierId: 1,
      carrierName: "Poczta Polska S.A.",
      services: [
        {
          serviceId: 1,
          serviceName: "List zwykły ekonomiczny D+4",
          serviceReturnFee: 4.99,
        },
      ],
    },
  ],
  papers: [
    {
      paperId: 3,
      paperName: "A4 100g",
    },
  ],
  envelopeTemplates: [
    {
      envelopeGroupName: "Koperty z logiem firmy",
      envelopeGroupDescription:
        "Koperty z logiem naszej firmy w lewym górnym rogu",
      envelope: [
        {
          envelopeId: 42,
          envelopeName: "Koperta C5",
          maxSheets: 10,
        },
      ],
    },
  ],
  statusCodes: [
    {
      code: "ACCEPTED",
      name: "Przesyłka przyjęta do realizacji",
      description:
        "Przesyłka została poprawnie zapisana w bazie i będzie procesowana zgodnie z parametrami.",
    },
  ],
};
```

## Fields

| Field                                                                    | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `carriers`                                                               | [models.MetadataResponseCarrier](../models/metadataresponsecarrier.md)[] | :heavy_minus_sign:                                                       | List of carriers and their available services.                           |
| `papers`                                                                 | [models.Paper](../models/paper.md)[]                                     | :heavy_minus_sign:                                                       | Available paper types.                                                   |
| `envelopeTemplates`                                                      | [models.EnvelopeTemplate](../models/envelopetemplate.md)[]               | :heavy_minus_sign:                                                       | Envelope template groups, each containing related templates.             |
| `statusCodes`                                                            | [models.StatusCode](../models/statuscode.md)[]                           | :heavy_minus_sign:                                                       | Available status codes.                                                  |