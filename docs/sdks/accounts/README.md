# Accounts
(*accounts*)

## Overview

### Available Operations

* [get](#get) - Retrieve account details
* [getSubaccount](#getsubaccount) - Get subaccount details

## get

Retrieve the current account balance and other account details. You can also check the account limit and whether the account is a **main** account. Main accounts have unrestricted privileges and, via the [User Panel](https://panel.postivo.pl), you can create as many subaccounts as needed.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getAccountDetails" method="get" path="/account" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.accounts.get();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClientCore } from "@postivo/postivo-client/core.js";
import { accountsGet } from "@postivo/postivo-client/funcs/accountsGet.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await accountsGet(client);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("accountsGet failed:", res.error);
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

**Promise\<[operations.GetAccountDetailsResponse](../../models/operations/getaccountdetailsresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 401, 403, 4XX            | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## getSubaccount

Check the account balance and other details, such as the subcredit balance of a subaccount. Subaccounts are additional users who can access your account’s services and data. You can restrict access levels and set privileges for subaccounts in the [User Panel](https://panel.postivo.pl).

Provide the full subaccount login to access its data.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getSubaccountDetails" method="get" path="/account/{user_login}" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.accounts.getSubaccount({
    userLogin: "some-login",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClientCore } from "@postivo/postivo-client/core.js";
import { accountsGetSubaccount } from "@postivo/postivo-client/funcs/accountsGetSubaccount.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await accountsGetSubaccount(client, {
    userLogin: "some-login",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("accountsGetSubaccount failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetSubaccountDetailsRequest](../../models/operations/getsubaccountdetailsrequest.md)                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetSubaccountDetailsResponse](../../models/operations/getsubaccountdetailsresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 401, 403, 404, 4XX       | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |