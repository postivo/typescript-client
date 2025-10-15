# ListMetadataResponse


## Supported Types

### `models.MetadataResponse`

```typescript
const value: models.MetadataResponse = {
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

### `models.ErrorResponse`

```typescript
const value: models.ErrorResponse = {
  type: "https://problems-registry.smartbear.com/invalid-body-property-format",
  status: 400,
  title: "Invalid Body property format",
  detail: "The request body contains a malformed property",
  code: "400-21",
  instance: "/rest/messages/sms",
};
```

