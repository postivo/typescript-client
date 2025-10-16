# ShipmentDocuments

Document payload to print and enclose into shipment. For a single document, provide `DocumentPdf`, `DocumentLibrary`, or `DocumentMock` (for checking the price only). For multiple documents, provide an array of `DocumentPdf`, `DocumentLibrary`, or `DocumentMock` objects (1–20).


## Supported Types

### `models.Documents`

```typescript
const value: models.Documents = {
  id: 887,
};
```

### `models.Documents[]`

```typescript
const value: models.Documents[] = [];
```

