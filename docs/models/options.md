# Options


## Supported Types

### `models.ShipmentOptions`

```typescript
const value: models.ShipmentOptions = {
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
  callback: {
    url: "https://example.com/callback",
    userToken: "75gh28hugjy8gfv6...",
  },
  miscInfo: {
    mpk: "dział handlowy",
    orderName: "Wysyłka zaproszeń",
  },
  rotateDocuments: false,
};
```

