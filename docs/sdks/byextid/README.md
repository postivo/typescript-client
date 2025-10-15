# ByExtId
(*addressBook.contacts.byExtId*)

## Overview

### Available Operations

* [get](#get) - Retrieve contact details by EXT_ID
* [update](#update) - Update a contact by EXT_ID
* [delete](#delete) - Delete a contact by EXT_ID
* [removeFromGroup](#removefromgroup) - Remove a contact from a group by EXT_ID
* [addToGroup](#addtogroup) - Add a contact to a group by EXT_ID

## get

Get the details of a contact from your Address Book using your external (custom) ID (the value you defined when creating the contact).

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getContactByExternalId" method="get" path="/contacts/external/{ext_id}" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.addressBook.contacts.byExtId.get({
    extId: "my-ext-id-44",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClientCore } from "@postivo/postivo-client/core.js";
import { addressBookContactsByExtIdGet } from "@postivo/postivo-client/funcs/addressBookContactsByExtIdGet.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await addressBookContactsByExtIdGet(client, {
    extId: "my-ext-id-44",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("addressBookContactsByExtIdGet failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetContactByExternalIdRequest](../../models/operations/getcontactbyexternalidrequest.md)                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetContactByExternalIdResponse](../../models/operations/getcontactbyexternalidresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 400, 401, 404, 4XX       | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## update

Update a contact by its external (custom) ID - the value you defined when creating the contact.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="updateContactByExternalId" method="put" path="/contacts/external/{ext_id}" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.addressBook.contacts.byExtId.update({
    extId: "my-id-2",
    contact: {
      name: "Jan Nowak",
      name2: "Firma Testowa Sp. z o.o.",
      address: "ul. Aleje Jerozolimskie",
      homeNumber: "31",
      flatNumber: "2",
      postCode: "00-999",
      city: "Warszawa",
      phoneNumber: "+48999999999",
      extId: "my-contact-1",
      groupIds: [
        13,
        534,
      ],
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
import { addressBookContactsByExtIdUpdate } from "@postivo/postivo-client/funcs/addressBookContactsByExtIdUpdate.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await addressBookContactsByExtIdUpdate(client, {
    extId: "my-id-2",
    contact: {
      name: "Jan Nowak",
      name2: "Firma Testowa Sp. z o.o.",
      address: "ul. Aleje Jerozolimskie",
      homeNumber: "31",
      flatNumber: "2",
      postCode: "00-999",
      city: "Warszawa",
      phoneNumber: "+48999999999",
      extId: "my-contact-1",
      groupIds: [
        13,
        534,
      ],
    },
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("addressBookContactsByExtIdUpdate failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.UpdateContactByExternalIdRequest](../../models/operations/updatecontactbyexternalidrequest.md)                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.UpdateContactByExternalIdResponse](../../models/operations/updatecontactbyexternalidresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 400, 401, 403, 404, 4XX  | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## delete

Remove a contact from your account by its external (custom) ID - the value defined when the contact was created.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="deleteContactByExternalId" method="delete" path="/contacts/external/{ext_id}" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.addressBook.contacts.byExtId.delete({
    extId: "my-id-2",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClientCore } from "@postivo/postivo-client/core.js";
import { addressBookContactsByExtIdDelete } from "@postivo/postivo-client/funcs/addressBookContactsByExtIdDelete.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await addressBookContactsByExtIdDelete(client, {
    extId: "my-id-2",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("addressBookContactsByExtIdDelete failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.DeleteContactByExternalIdRequest](../../models/operations/deletecontactbyexternalidrequest.md)                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.DeleteContactByExternalIdResponse](../../models/operations/deletecontactbyexternalidresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 400, 401, 403, 404, 4XX  | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## removeFromGroup

Remove a contact from a group in your Address Book using the contact’s external (custom) ID. This operation does not delete the contact; it only detaches the contact from the group. Provide the contact’s `ext_id` and the group’s `group_id` parameters to perform the detachment.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="removeContactByExtIdToGroup" method="delete" path="/contacts/external/{ext_id}/group/{group_id}" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.addressBook.contacts.byExtId.removeFromGroup({
    extId: "my-id-1",
    groupId: 656,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClientCore } from "@postivo/postivo-client/core.js";
import { addressBookContactsByExtIdRemoveFromGroup } from "@postivo/postivo-client/funcs/addressBookContactsByExtIdRemoveFromGroup.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await addressBookContactsByExtIdRemoveFromGroup(client, {
    extId: "my-id-1",
    groupId: 656,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("addressBookContactsByExtIdRemoveFromGroup failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.RemoveContactByExtIdToGroupRequest](../../models/operations/removecontactbyextidtogrouprequest.md)                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.RemoveContactByExtIdToGroupResponse](../../models/operations/removecontactbyextidtogroupresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 404                      | application/json         |
| errors.ErrorResponse     | 400, 401, 403, 4XX       | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## addToGroup

Assign a contact to a group using the contact’s external (custom) ID (assigned when creating the contact). If a contact and a group exist in your account, you can add the contact to that group.

Provide the contact’s `ext_id` and the group’s `group_id` parameters to perform the assignment.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="addContactByExtIdToGroup" method="patch" path="/contacts/external/{ext_id}/group/{group_id}" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.addressBook.contacts.byExtId.addToGroup({
    extId: "my-id-1",
    groupId: 656,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClientCore } from "@postivo/postivo-client/core.js";
import { addressBookContactsByExtIdAddToGroup } from "@postivo/postivo-client/funcs/addressBookContactsByExtIdAddToGroup.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await addressBookContactsByExtIdAddToGroup(client, {
    extId: "my-id-1",
    groupId: 656,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("addressBookContactsByExtIdAddToGroup failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AddContactByExtIdToGroupRequest](../../models/operations/addcontactbyextidtogrouprequest.md)                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.AddContactByExtIdToGroupResponse](../../models/operations/addcontactbyextidtogroupresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 404                      | application/json         |
| errors.ErrorResponse     | 400, 401, 403, 4XX       | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |