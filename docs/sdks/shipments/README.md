# Shipments
(*shipments*)

## Overview

### Available Operations

* [status](#status) - Retrieve shipment details with status events
* [cancel](#cancel) - Cancel shipments
* [dispatch](#dispatch) - Dispatch a new shipment
* [documents](#documents) - Retrieve documents related to a shipment
* [price](#price) - Check the shipment price

## status

Retrieve the current status and details for one or more shipments by their `ids`. Pass the unique shipment IDs (returned when the shipments were created) as a path parameter. To query provide a list (up to **50** IDs per call). For larger batches, split the requests.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getStatus" method="get" path="/shipment/{ids}" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.shipments.status({
    ids: [
      "A0043456",
    ],
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClientCore } from "@postivo/postivo-client/core.js";
import { shipmentsStatus } from "@postivo/postivo-client/funcs/shipmentsStatus.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await shipmentsStatus(client, {
    ids: [
      "A0043456",
    ],
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("shipmentsStatus failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetStatusRequest](../../models/operations/getstatusrequest.md)                                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetStatusResponse](../../models/operations/getstatusresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 400, 401, 403, 404, 4XX  | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## cancel

Cancel shipments that have not yet been processed by their `ids`. Pass the unique shipment IDs (returned when the shipment was created) as a parameter. To cancel multiple shipments at once, provide a list of IDs (up to **50** per call). For larger volumes, split the operation into multiple requests. Only shipments with status `ACCEPTED` can be cancelled.

If duplicate shipment IDs are provided in a single call, the API processes each unique ID only once.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="cancelShipment" method="delete" path="/shipment/{ids}" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.shipments.cancel({
    ids: [
      "A0043456",
    ],
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClientCore } from "@postivo/postivo-client/core.js";
import { shipmentsCancel } from "@postivo/postivo-client/funcs/shipmentsCancel.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await shipmentsCancel(client, {
    ids: [
      "A0043456",
    ],
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("shipmentsCancel failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.CancelShipmentRequest](../../models/operations/cancelshipmentrequest.md)                                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.CancelShipmentResponse](../../models/operations/cancelshipmentresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 400, 401, 403, 404, 4XX  | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## dispatch

Send a shipment to one or multiple recipients in a single request. Provide a `Shipment` object. The object includes properties that define the shipment (recipient details, included documents, and optional settings). Some fields are required.

The system accepts up to **50** recipients per call. For larger volumes, split the operation into multiple requests.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="shipmentDispatch" method="post" path="/shipment" -->
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

### Standalone function

The standalone function version of this method:

```typescript
import { ClientCore } from "@postivo/postivo-client/core.js";
import { shipmentsDispatch } from "@postivo/postivo-client/funcs/shipmentsDispatch.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await shipmentsDispatch(client, {
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
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("shipmentsDispatch failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.Shipment](../../models/shipment.md)                                                                                                                                    | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.ShipmentDispatchResponse](../../models/operations/shipmentdispatchresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 400, 401, 403, 4XX       | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## documents

Download documents related to a shipment by its `id`. Pass the unique shipment `id` (returned when the shipment was created) as a parameter. The second parameter is the document type to download. Supported document types include: dispatch certificate, envelope template, and EPO (in PDF or XML formats).

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getDocuments" method="get" path="/shipment/{id}/document/{type}" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.shipments.documents({
    id: "A0043456",
    type: "dispatch_cert",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClientCore } from "@postivo/postivo-client/core.js";
import { shipmentsDocuments } from "@postivo/postivo-client/funcs/shipmentsDocuments.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await shipmentsDocuments(client, {
    id: "A0043456",
    type: "dispatch_cert",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("shipmentsDocuments failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetDocumentsRequest](../../models/operations/getdocumentsrequest.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetDocumentsResponse](../../models/operations/getdocumentsresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 400, 401, 403, 404, 4XX  | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## price

Check the price of a shipment for one or multiple recipients. Provide a `Shipment` object in the request. Each object includes properties such as recipient details, included documents, and optional settings. Some fields are required.

The system accepts up to **50** recipients per call. For larger volumes, split the operation into multiple requests.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="shipmentPrice" method="post" path="/shipment/price" -->
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

### Standalone function

The standalone function version of this method:

```typescript
import { ClientCore } from "@postivo/postivo-client/core.js";
import { shipmentsPrice } from "@postivo/postivo-client/funcs/shipmentsPrice.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await shipmentsPrice(client, {
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
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("shipmentsPrice failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.Shipment](../../models/shipment.md)                                                                                                                                    | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.ShipmentPriceResponse](../../models/operations/shipmentpriceresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 400, 401, 403, 4XX       | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |