# Shipment

Properties of a new shipment.

## Example Usage

```typescript
import { Shipment } from "@postivo/postivo-client/models";
import { RFCDate } from "@postivo/postivo-client/types";

let value: Shipment = {
  recipients: {
    extId: "marcin-344",
    fromShared: true,
    customId: "my-id-1113",
    postscript: "Do rąk własnych",
  },
  documents: {
    fileStream: "<file content in base64 format>",
    fileName: "document1.pdf",
  },
  options: {
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
  },
};
```

## Fields

| Field                                                                                                                                                                                                                                  | Type                                                                                                                                                                                                                                   | Required                                                                                                                                                                                                                               | Description                                                                                                                                                                                                                            |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `recipients`                                                                                                                                                                                                                           | *models.Recipients2*                                                                                                                                                                                                                   | :heavy_check_mark:                                                                                                                                                                                                                     | Recipient data for a single shipment. For one recipient, provide a `RecipientInline`, `RecipientFromAddressBook`, or `RecipientFromAddressBookByExternalId` object. For multiple recipients, provide an array of these objects (1–50). |
| `documents`                                                                                                                                                                                                                            | *models.Documents2*                                                                                                                                                                                                                    | :heavy_check_mark:                                                                                                                                                                                                                     | Document payload to print and enclose. For a single document, provide `DocumentPdf` or `DocumentLibrary`. For multiple documents, provide an array of `DocumentPdf`, `DocumentLibrary`, or `DocumentMock` objects (1–20).              |
| `options`                                                                                                                                                                                                                              | *models.Options*                                                                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                                                                                     | N/A                                                                                                                                                                                                                                    |