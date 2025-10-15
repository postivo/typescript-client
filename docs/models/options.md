# Options


## Supported Types

### `models.RequestOptions`

```typescript
const value: models.RequestOptions = {
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

