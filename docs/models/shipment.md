# Shipment

Properties of a new shipment.

## Example Usage

```typescript
import { Shipment } from "@postivo/postivo-client/models";
import { RFCDate } from "@postivo/postivo-client/types";

let value: Shipment = {
  recipients: [],
  documents: [
    {
      fileStream: "<file content in base64 format>",
      fileName: "document1.pdf",
    },
  ],
  options: {
    predefinedConfigId: 32,
    inlineConfig: null,
    senderId: 567,
    dispatchDate: new RFCDate("2025-12-24"),
    callback: {
      url: "https://example.com/callback",
      userToken: "75gh28hugjy8gfv6...",
    },
    miscInfo: null,
    rotateDocuments: false,
  },
};
```

## Fields

| Field                                                                                                                                                                                                                                                                                  | Type                                                                                                                                                                                                                                                                                   | Required                                                                                                                                                                                                                                                                               | Description                                                                                                                                                                                                                                                                            |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `recipients`                                                                                                                                                                                                                                                                           | *models.ShipmentRecipients*                                                                                                                                                                                                                                                            | :heavy_check_mark:                                                                                                                                                                                                                                                                     | Recipient data for a single shipment. For one recipient, provide a `RecipientInline`, `RecipientFromAddressBook`, or `RecipientFromAddressBookByExternalId` object. For multiple recipients, provide an array of these objects (1–50).                                                 |
| `documents`                                                                                                                                                                                                                                                                            | *models.ShipmentDocuments*                                                                                                                                                                                                                                                             | :heavy_check_mark:                                                                                                                                                                                                                                                                     | Document payload to print and enclose into shipment. For a single document, provide `DocumentPdf`, `DocumentLibrary`, or `DocumentMock` (for checking the price only). For multiple documents, provide an array of `DocumentPdf`, `DocumentLibrary`, or `DocumentMock` objects (1–20). |
| `options`                                                                                                                                                                                                                                                                              | *models.Options*                                                                                                                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                                                                                                                                     | N/A                                                                                                                                                                                                                                                                                    |