# Documents2

Document payload to print and enclose. For a single document, provide `DocumentPdf` or `DocumentLibrary`. For multiple documents, provide an array of `DocumentPdf`, `DocumentLibrary`, or `DocumentMock` objects (1–20).


## Supported Types

### `models.DocumentPdf`

```typescript
const value: models.DocumentPdf = {
  fileStream: "<file content in base64 format>",
  fileName: "document1.pdf",
};
```

### `models.DocumentLibrary`

```typescript
const value: models.DocumentLibrary = {
  id: 887,
};
```

### `models.DocumentMock`

```typescript
const value: models.DocumentMock = {
  pages: 3,
};
```

### `models.Documents1[]`

```typescript
const value: models.Documents1[] = [];
```

