[![NPM Version (with dist tag)](https://img.shields.io/npm/v/%40postivo/postivo-client)](https://www.npmjs.com/package/@postivo/postivo-client)
[![GitHub License](https://img.shields.io/github/license/postivo/typescript-client)](https://github.com/postivo/typescript-client/blob/main/LICENSE)
[![Static Badge](https://img.shields.io/badge/built_by-Speakeasy-yellow)](https://www.speakeasy.com/?utm_source=postivo-client&utm_campaign=typescript)

# POSTIVO.PL REST API Client SDK for TypeScript (@postivo/postivo-client)

This package provides the **POSTIVO.PL Hybrid Mail Services SDK** for Typescript, allowing you to dispatch shipments directly from your application via the [POSTIVO.PL](https://postivo.pl) platform.

## Additional documentation:

Comprehensive documentation of all methods and types is available below in [Available Resources and Operations](#available-resources-and-operations).

You can also refer to the [REST API v1 documentation](https://api.postivo.pl/rest/v1/) for additional details about this SDK.
<!-- No Summary [summary] -->
<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [POSTIVO.PL REST API Client SDK for TypeScript (@postivo/postivo-client)](#postivopl-rest-api-client-sdk-for-typescript-postivopostivo-client)
  * [Additional documentation:](#additional-documentation)
  * [SDK Installation](#sdk-installation)
  * [Requirements](#requirements)
  * [SDK Example Usage](#sdk-example-usage)
  * [Authentication](#authentication)
  * [Available Resources and Operations](#available-resources-and-operations)
  * [Standalone functions](#standalone-functions)
  * [Retries](#retries)
  * [Error Handling](#error-handling)
  * [Server Selection](#server-selection)
  * [Custom HTTP Client](#custom-http-client)
  * [Debugging](#debugging)
* [Development](#development)
  * [Maturity](#maturity)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start SDK Installation [installation] -->
## SDK Installation

The SDK can be installed with either [npm](https://www.npmjs.com/), [pnpm](https://pnpm.io/), [bun](https://bun.sh/) or [yarn](https://classic.yarnpkg.com/en/) package managers.

### NPM

```bash
npm add @postivo/postivo-client
```

### PNPM

```bash
pnpm add @postivo/postivo-client
```

### Bun

```bash
bun add @postivo/postivo-client
```

### Yarn

```bash
yarn add @postivo/postivo-client
```

> [!NOTE]
> This package is published with CommonJS and ES Modules (ESM) support.
<!-- End SDK Installation [installation] -->

<!-- Start Requirements [requirements] -->
## Requirements

For supported JavaScript runtimes, please consult [RUNTIMES.md](RUNTIMES.md).
<!-- End Requirements [requirements] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

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

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security scheme globally:

| Name     | Type | Scheme      | Environment Variable |
| -------- | ---- | ----------- | -------------------- |
| `bearer` | http | HTTP Bearer | `CLIENT_BEARER`      |

To authenticate with the API the `bearer` parameter must be set when initializing the SDK client instance. For example:
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
<!-- End Authentication [security] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

<details open>
<summary>Available methods</summary>

### [accounts](docs/sdks/accounts/README.md)

* [get](docs/sdks/accounts/README.md#get) - Retrieve account details
* [getSubaccount](docs/sdks/accounts/README.md#getsubaccount) - Get subaccount details

#### [addressBook.contacts](docs/sdks/contacts/README.md)

* [list](docs/sdks/contacts/README.md#list) - List contacts
* [add](docs/sdks/contacts/README.md#add) - Add a new contact
* [get](docs/sdks/contacts/README.md#get) - Retrieve contact details
* [update](docs/sdks/contacts/README.md#update) - Update a contact
* [delete](docs/sdks/contacts/README.md#delete) - Delete a contact
* [removeFromGroup](docs/sdks/contacts/README.md#removefromgroup) - Remove a contact from a group
* [addToGroup](docs/sdks/contacts/README.md#addtogroup) - Add a contact to a group

#### [addressBook.contacts.byExtId](docs/sdks/byextid/README.md)

* [get](docs/sdks/byextid/README.md#get) - Retrieve contact details by EXT_ID
* [update](docs/sdks/byextid/README.md#update) - Update a contact by EXT_ID
* [delete](docs/sdks/byextid/README.md#delete) - Delete a contact by EXT_ID
* [removeFromGroup](docs/sdks/byextid/README.md#removefromgroup) - Remove a contact from a group by EXT_ID
* [addToGroup](docs/sdks/byextid/README.md#addtogroup) - Add a contact to a group by EXT_ID

#### [addressBook.groups](docs/sdks/groups/README.md)

* [list](docs/sdks/groups/README.md#list) - List groups
* [add](docs/sdks/groups/README.md#add) - Add a new group
* [get](docs/sdks/groups/README.md#get) - Retrieve group details
* [update](docs/sdks/groups/README.md#update) - Update a group
* [delete](docs/sdks/groups/README.md#delete) - Delete a group

### [common](docs/sdks/common/README.md)

* [ping](docs/sdks/common/README.md#ping) - Check API availability and version

### [metadata](docs/sdks/metadata/README.md)

* [list](docs/sdks/metadata/README.md#list) - List metadata
* [getPredefinedConfigs](docs/sdks/metadata/README.md#getpredefinedconfigs) - List predefined configs

### [senders](docs/sdks/senders/README.md)

* [list](docs/sdks/senders/README.md#list) - List senders
* [add](docs/sdks/senders/README.md#add) - Add a new sender
* [delete](docs/sdks/senders/README.md#delete) - Delete a sender
* [verify](docs/sdks/senders/README.md#verify) - Verify sender

### [shipments](docs/sdks/shipments/README.md)

* [status](docs/sdks/shipments/README.md#status) - Retrieve shipment details with status events
* [cancel](docs/sdks/shipments/README.md#cancel) - Cancel shipments
* [dispatch](docs/sdks/shipments/README.md#dispatch) - Dispatch a new shipment
* [documents](docs/sdks/shipments/README.md#documents) - Retrieve documents related to a shipment
* [price](docs/sdks/shipments/README.md#price) - Check the shipment price

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Standalone functions [standalone-funcs] -->
## Standalone functions

All the methods listed above are available as standalone functions. These
functions are ideal for use in applications running in the browser, serverless
runtimes or other environments where application bundle size is a primary
concern. When using a bundler to build your application, all unused
functionality will be either excluded from the final bundle or tree-shaken away.

To read more about standalone functions, check [FUNCTIONS.md](./FUNCTIONS.md).

<details>

<summary>Available standalone functions</summary>

- [`accountsGet`](docs/sdks/accounts/README.md#get) - Retrieve account details
- [`accountsGetSubaccount`](docs/sdks/accounts/README.md#getsubaccount) - Get subaccount details
- [`addressBookContactsAdd`](docs/sdks/contacts/README.md#add) - Add a new contact
- [`addressBookContactsAddToGroup`](docs/sdks/contacts/README.md#addtogroup) - Add a contact to a group
- [`addressBookContactsByExtIdAddToGroup`](docs/sdks/byextid/README.md#addtogroup) - Add a contact to a group by EXT_ID
- [`addressBookContactsByExtIdDelete`](docs/sdks/byextid/README.md#delete) - Delete a contact by EXT_ID
- [`addressBookContactsByExtIdGet`](docs/sdks/byextid/README.md#get) - Retrieve contact details by EXT_ID
- [`addressBookContactsByExtIdRemoveFromGroup`](docs/sdks/byextid/README.md#removefromgroup) - Remove a contact from a group by EXT_ID
- [`addressBookContactsByExtIdUpdate`](docs/sdks/byextid/README.md#update) - Update a contact by EXT_ID
- [`addressBookContactsDelete`](docs/sdks/contacts/README.md#delete) - Delete a contact
- [`addressBookContactsGet`](docs/sdks/contacts/README.md#get) - Retrieve contact details
- [`addressBookContactsList`](docs/sdks/contacts/README.md#list) - List contacts
- [`addressBookContactsRemoveFromGroup`](docs/sdks/contacts/README.md#removefromgroup) - Remove a contact from a group
- [`addressBookContactsUpdate`](docs/sdks/contacts/README.md#update) - Update a contact
- [`addressBookGroupsAdd`](docs/sdks/groups/README.md#add) - Add a new group
- [`addressBookGroupsDelete`](docs/sdks/groups/README.md#delete) - Delete a group
- [`addressBookGroupsGet`](docs/sdks/groups/README.md#get) - Retrieve group details
- [`addressBookGroupsList`](docs/sdks/groups/README.md#list) - List groups
- [`addressBookGroupsUpdate`](docs/sdks/groups/README.md#update) - Update a group
- [`commonPing`](docs/sdks/common/README.md#ping) - Check API availability and version
- [`metadataGetPredefinedConfigs`](docs/sdks/metadata/README.md#getpredefinedconfigs) - List predefined configs
- [`metadataList`](docs/sdks/metadata/README.md#list) - List metadata
- [`sendersAdd`](docs/sdks/senders/README.md#add) - Add a new sender
- [`sendersDelete`](docs/sdks/senders/README.md#delete) - Delete a sender
- [`sendersList`](docs/sdks/senders/README.md#list) - List senders
- [`sendersVerify`](docs/sdks/senders/README.md#verify) - Verify sender
- [`shipmentsCancel`](docs/sdks/shipments/README.md#cancel) - Cancel shipments
- [`shipmentsDispatch`](docs/sdks/shipments/README.md#dispatch) - Dispatch a new shipment
- [`shipmentsDocuments`](docs/sdks/shipments/README.md#documents) - Retrieve documents related to a shipment
- [`shipmentsPrice`](docs/sdks/shipments/README.md#price) - Check the shipment price
- [`shipmentsStatus`](docs/sdks/shipments/README.md#status) - Retrieve shipment details with status events

</details>
<!-- End Standalone functions [standalone-funcs] -->

<!-- Start Retries [retries] -->
## Retries

Some of the endpoints in this SDK support retries.  If you use the SDK without any configuration, it will fall back to the default retry strategy provided by the API.  However, the default retry strategy can be overridden on a per-operation basis, or across the entire SDK.

To change the default retry strategy for a single API call, simply provide a retryConfig object to the call:
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.accounts.get({
    retries: {
      strategy: "backoff",
      backoff: {
        initialInterval: 1,
        maxInterval: 50,
        exponent: 1.1,
        maxElapsedTime: 100,
      },
      retryConnectionErrors: false,
    },
  });

  console.log(result);
}

run();

```

If you'd like to override the default retry strategy for all operations that support retries, you can provide a retryConfig at SDK initialization:
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  retryConfig: {
    strategy: "backoff",
    backoff: {
      initialInterval: 1,
      maxInterval: 50,
      exponent: 1.1,
      maxElapsedTime: 100,
    },
    retryConnectionErrors: false,
  },
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.accounts.get();

  console.log(result);
}

run();

```
<!-- End Retries [retries] -->

<!-- Start Error Handling [errors] -->
## Error Handling

[`ClientError`](./src/models/errors/clienterror.ts) is the base class for all HTTP error responses. It has the following properties:

| Property            | Type       | Description                                                                             |
| ------------------- | ---------- | --------------------------------------------------------------------------------------- |
| `error.message`     | `string`   | Error message                                                                           |
| `error.statusCode`  | `number`   | HTTP response status code eg `404`                                                      |
| `error.headers`     | `Headers`  | HTTP response headers                                                                   |
| `error.body`        | `string`   | HTTP body. Can be empty string if no body is returned.                                  |
| `error.rawResponse` | `Response` | Raw HTTP response                                                                       |
| `error.data$`       |            | Optional. Some errors may contain structured data. [See Error Classes](#error-classes). |

### Example
```typescript
import { Client } from "@postivo/postivo-client";
import * as errors from "@postivo/postivo-client/models/errors";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  try {
    const result = await client.accounts.get();

    console.log(result);
  } catch (error) {
    // The base class for HTTP error responses
    if (error instanceof errors.ClientError) {
      console.log(error.message);
      console.log(error.statusCode);
      console.log(error.body);
      console.log(error.headers);

      // Depending on the method different errors may be thrown
      if (error instanceof errors.ErrorResponse) {
        console.log(error.data$.type); // string
        console.log(error.data$.status); // number
        console.log(error.data$.title); // string
        console.log(error.data$.detail); // string
        console.log(error.data$.code); // string
      }
    }
  }
}

run();

```

### Error Classes
**Primary errors:**
* [`ClientError`](./src/models/errors/clienterror.ts): The base class for HTTP error responses.
  * [`ErrorResponse`](./src/models/errors/errorresponse.ts): Problem Details object (RFC 9457) describing the error.

<details><summary>Less common errors (6)</summary>

<br />

**Network errors:**
* [`ConnectionError`](./src/models/errors/httpclienterrors.ts): HTTP client was unable to make a request to a server.
* [`RequestTimeoutError`](./src/models/errors/httpclienterrors.ts): HTTP request timed out due to an AbortSignal signal.
* [`RequestAbortedError`](./src/models/errors/httpclienterrors.ts): HTTP request was aborted by the client.
* [`InvalidRequestError`](./src/models/errors/httpclienterrors.ts): Any input used to create a request is invalid.
* [`UnexpectedClientError`](./src/models/errors/httpclienterrors.ts): Unrecognised or unexpected error.


**Inherit from [`ClientError`](./src/models/errors/clienterror.ts)**:
* [`ResponseValidationError`](./src/models/errors/responsevalidationerror.ts): Type mismatch between the data returned from the server and the structure expected by the SDK. See `error.rawValue` for the raw value and `error.pretty()` for a nicely formatted multi-line string.

</details>
<!-- End Error Handling [errors] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Select Server by Name

You can override the default server globally by passing a server name to the `server: keyof typeof ServerList` optional parameter when initializing the SDK client instance. The selected server will then be used as the default on the operations that use it. This table lists the names associated with the available servers:

| Name      | Server                                   | Description           |
| --------- | ---------------------------------------- | --------------------- |
| `prod`    | `https://api.postivo.pl/rest/v1`         | Production system     |
| `sandbox` | `https://api.postivo.pl/rest-sandbox/v1` | Test system (SANDBOX) |

#### Example

```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  server: "sandbox",
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.accounts.get();

  console.log(result);
}

run();

```

### Override Server URL Per-Client

The default server can also be overridden globally by passing a URL to the `serverURL: string` optional parameter when initializing the SDK client instance. For example:
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  serverURL: "https://api.postivo.pl/rest/v1",
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.accounts.get();

  console.log(result);
}

run();

```
<!-- End Server Selection [server] -->

<!-- Start Custom HTTP Client [http-client] -->
## Custom HTTP Client

The TypeScript SDK makes API calls using an `HTTPClient` that wraps the native
[Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API). This
client is a thin wrapper around `fetch` and provides the ability to attach hooks
around the request lifecycle that can be used to modify the request or handle
errors and response.

The `HTTPClient` constructor takes an optional `fetcher` argument that can be
used to integrate a third-party HTTP client or when writing tests to mock out
the HTTP client and feed in fixtures.

The following example shows how to use the `"beforeRequest"` hook to to add a
custom header and a timeout to requests and how to use the `"requestError"` hook
to log errors:

```typescript
import { Client } from "@postivo/postivo-client";
import { HTTPClient } from "@postivo/postivo-client/lib/http";

const httpClient = new HTTPClient({
  // fetcher takes a function that has the same signature as native `fetch`.
  fetcher: (request) => {
    return fetch(request);
  }
});

httpClient.addHook("beforeRequest", (request) => {
  const nextRequest = new Request(request, {
    signal: request.signal || AbortSignal.timeout(5000)
  });

  nextRequest.headers.set("x-custom-header", "custom value");

  return nextRequest;
});

httpClient.addHook("requestError", (error, request) => {
  console.group("Request Error");
  console.log("Reason:", `${error}`);
  console.log("Endpoint:", `${request.method} ${request.url}`);
  console.groupEnd();
});

const sdk = new Client({ httpClient: httpClient });
```
<!-- End Custom HTTP Client [http-client] -->

<!-- Start Debugging [debug] -->
## Debugging

You can setup your SDK to emit debug logs for SDK requests and responses.

You can pass a logger that matches `console`'s interface as an SDK option.

> [!WARNING]
> Beware that debug logging will reveal secrets, like API tokens in headers, in log messages printed to a console or files. It's recommended to use this feature only during local development and not in production.

```typescript
import { Client } from "@postivo/postivo-client";

const sdk = new Client({ debugLogger: console });
```

You can also enable a default debug logger by setting an environment variable `CLIENT_DEBUG` to true.
<!-- End Debugging [debug] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This SDK is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release.