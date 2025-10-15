<!-- Start SDK Example Usage [usage] -->
### Sending Shipment to single recipient

This example demonstrates simple sending Shipment to a single recipient:

```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.shipments.dispatch({
    recipients: {
      name: "Jan Nowak",
      name2: "Firma testowa Sp. z o.o.",
      address: "ul. Testowa",
      homeNumber: "23",
      flatNumber: "2",
      postCode: "00-999",
      city: "Warszawa",
      country: "PL",
      phoneNumber: "+48666666666",
      postscript: "Komunikat",
      customId: "1234567890",
    },
    documents: [
      {
        fileStream: "<document_1 content encoded to base64>",
        fileName: "document1.pdf",
      },
      {
        fileStream: "<document_2 content encoded to base64>",
        fileName: "document2.pdf",
      },
    ],
    options: {
      predefinedConfigId: 2670,
    },
  });

  console.log(result);
}

run();

```

### Checking the price of a shipment for single recipient

This example demonstrates simple checking the price of a Shipment to a single recipient:

```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.shipments.price({
    recipients: {
      name: "Jan Nowak",
      name2: "Firma testowa Sp. z o.o.",
      address: "ul. Testowa",
      homeNumber: "23",
      flatNumber: "2",
      postCode: "00-999",
      city: "Warszawa",
      country: "PL",
      phoneNumber: "+48666666666",
      postscript: "Komunikat",
      customId: "1234567890",
    },
    documents: [
      {
        fileStream: "<document_1 content encoded to base64>",
        fileName: "document1.pdf",
      },
      {
        fileStream: "<document_2 content encoded to base64>",
        fileName: "document2.pdf",
      },
    ],
    options: {
      predefinedConfigId: 2670,
    },
  });

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->