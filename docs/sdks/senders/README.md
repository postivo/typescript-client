# Senders
(*senders*)

## Overview

### Available Operations

* [list](#list) - List senders
* [add](#add) - Add a new sender
* [delete](#delete) - Delete a sender
* [verify](#verify) - Verify sender

## list

Retrieve the list of allowed senders defined in your account. Senders are registered in your account and must be verified and activated before use. Activated senders have `active: true` property and can be used to send shipments. Inactive senders are also returned (`active: false`), but cannot be used until activated.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="listSenders" method="get" path="/senders" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.senders.list();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClientCore } from "@postivo/postivo-client/core.js";
import { sendersList } from "@postivo/postivo-client/funcs/sendersList.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await sendersList(client);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("sendersList failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.ListSendersResponse](../../models/operations/listsendersresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 400, 401, 403, 4XX       | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## add

Create a new sender on your account. The request must contain a `Sender` object. To prevent fraud, all additional senders are verified by mailing a verification code to the sender’s address. Complete the verification using the `verifySender` method. Verified senders have `active: true` and can be used to send shipments. Inactive senders are also returned (`active: false`), but cannot be used until verification is completed.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="addSender" method="post" path="/senders" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.senders.add({
    name: "Jan Nowak",
    name2: "Firma Testowa Sp. z o.o.",
    address: "ul. Aleje Jerozolimskie",
    homeNumber: "31",
    flatNumber: "2",
    postCode: "00-999",
    city: "Warszawa",
    country: "PL",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClientCore } from "@postivo/postivo-client/core.js";
import { sendersAdd } from "@postivo/postivo-client/funcs/sendersAdd.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await sendersAdd(client, {
    name: "Jan Nowak",
    name2: "Firma Testowa Sp. z o.o.",
    address: "ul. Aleje Jerozolimskie",
    homeNumber: "31",
    flatNumber: "2",
    postCode: "00-999",
    city: "Warszawa",
    country: "PL",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("sendersAdd failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.Sender](../../models/sender.md)                                                                                                                                        | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.AddSenderResponse](../../models/operations/addsenderresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 400, 401, 403, 4XX       | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## delete

Remove a sender from your account by `id`. Pass the sender’s `id` parameter to remove it. The sender is deleted immediately.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="deleteSender" method="delete" path="/senders/{id}" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.senders.delete({
    id: 14,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClientCore } from "@postivo/postivo-client/core.js";
import { sendersDelete } from "@postivo/postivo-client/funcs/sendersDelete.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await sendersDelete(client, {
    id: 14,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("sendersDelete failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.DeleteSenderRequest](../../models/operations/deletesenderrequest.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.DeleteSenderResponse](../../models/operations/deletesenderresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 400, 401, 403, 404, 4XX  | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## verify

Verify a sender to activate it. After adding a new sender, a letter containing a verification code is mailed to the sender’s address. Provide this code to complete verification.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="verifySender" method="patch" path="/senders/{id}" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.senders.verify({
    id: 443,
    requestBody: {
      verificationCode: "A345FP73",
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
import { sendersVerify } from "@postivo/postivo-client/funcs/sendersVerify.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await sendersVerify(client, {
    id: 443,
    requestBody: {
      verificationCode: "A345FP73",
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("sendersVerify failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.VerifySenderRequest](../../models/operations/verifysenderrequest.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.VerifySenderResponse](../../models/operations/verifysenderresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 404                      | application/json         |
| errors.ErrorResponse     | 400, 401, 403, 4XX       | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |