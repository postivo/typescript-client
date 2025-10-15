# Contacts
(*addressBook.contacts*)

## Overview

### Available Operations

* [list](#list) - List contacts
* [add](#add) - Add a new contact
* [get](#get) - Retrieve contact details
* [update](#update) - Update a contact
* [delete](#delete) - Delete a contact
* [removeFromGroup](#removefromgroup) - Remove a contact from a group
* [addToGroup](#addtogroup) - Add a contact to a group

## list

Retrieve a paginated list of all contacts defined in your account’s **Address Book**.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="listContacts" method="get" path="/contacts" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.addressBook.contacts.list({});

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClientCore } from "@postivo/postivo-client/core.js";
import { addressBookContactsList } from "@postivo/postivo-client/funcs/addressBookContactsList.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await addressBookContactsList(client, {});
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("addressBookContactsList failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ListContactsRequest](../../models/operations/listcontactsrequest.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.ListContactsResponse](../../models/operations/listcontactsresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 400, 401, 403, 4XX       | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## add

Create a new contact in your account’s **Address Book**.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="addContact" method="post" path="/contacts" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.addressBook.contacts.add({
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
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { ClientCore } from "@postivo/postivo-client/core.js";
import { addressBookContactsAdd } from "@postivo/postivo-client/funcs/addressBookContactsAdd.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await addressBookContactsAdd(client, {
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
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("addressBookContactsAdd failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.Contact](../../models/contact.md)                                                                                                                                      | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.AddContactResponse](../../models/operations/addcontactresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 400, 401, 403, 4XX       | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## get

Get the details of a contact from your Address Book using its global `id`.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getContactById" method="get" path="/contacts/{id}" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.addressBook.contacts.get({
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
import { addressBookContactsGet } from "@postivo/postivo-client/funcs/addressBookContactsGet.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await addressBookContactsGet(client, {
    id: 14,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("addressBookContactsGet failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetContactByIdRequest](../../models/operations/getcontactbyidrequest.md)                                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetContactByIdResponse](../../models/operations/getcontactbyidresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 400, 401, 404, 4XX       | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## update

Update a contact by its global ID.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="updateContact" method="put" path="/contacts/{id}" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.addressBook.contacts.update({
    id: 14,
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
import { addressBookContactsUpdate } from "@postivo/postivo-client/funcs/addressBookContactsUpdate.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await addressBookContactsUpdate(client, {
    id: 14,
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
    console.log("addressBookContactsUpdate failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.UpdateContactRequest](../../models/operations/updatecontactrequest.md)                                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.UpdateContactResponse](../../models/operations/updatecontactresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 400, 401, 403, 404, 4XX  | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## delete

Remove a contact from your account by system ID.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="deleteContact" method="delete" path="/contacts/{id}" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.addressBook.contacts.delete({
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
import { addressBookContactsDelete } from "@postivo/postivo-client/funcs/addressBookContactsDelete.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await addressBookContactsDelete(client, {
    id: 14,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("addressBookContactsDelete failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.DeleteContactRequest](../../models/operations/deletecontactrequest.md)                                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.DeleteContactResponse](../../models/operations/deletecontactresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 400, 401, 403, 404, 4XX  | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## removeFromGroup

Remove a contact from a group in your Address Book. This does not delete the contact; it only detaches the contact from the group.

Provide the contact’s `id` and the group’s `group_id` parameters to perform the detachment.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="removeContactFromGroup" method="delete" path="/contacts/{id}/group/{group_id}" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.addressBook.contacts.removeFromGroup({
    id: 35,
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
import { addressBookContactsRemoveFromGroup } from "@postivo/postivo-client/funcs/addressBookContactsRemoveFromGroup.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await addressBookContactsRemoveFromGroup(client, {
    id: 35,
    groupId: 656,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("addressBookContactsRemoveFromGroup failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.RemoveContactFromGroupRequest](../../models/operations/removecontactfromgrouprequest.md)                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.RemoveContactFromGroupResponse](../../models/operations/removecontactfromgroupresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 404                      | application/json         |
| errors.ErrorResponse     | 400, 401, 403, 4XX       | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |

## addToGroup

Assign a contact to a group. If a contact and a group exist in your account, you can add the contact to that group.

Provide the contact’s `id` and the group’s `group_id` parameters to perform the assignment.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="addContactToGroup" method="patch" path="/contacts/{id}/group/{group_id}" -->
```typescript
import { Client } from "@postivo/postivo-client";

const client = new Client({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const result = await client.addressBook.contacts.addToGroup({
    id: 35,
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
import { addressBookContactsAddToGroup } from "@postivo/postivo-client/funcs/addressBookContactsAddToGroup.js";

// Use `ClientCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const client = new ClientCore({
  bearer: "<YOUR API ACCESS TOKEN>",
});

async function run() {
  const res = await addressBookContactsAddToGroup(client, {
    id: 35,
    groupId: 656,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("addressBookContactsAddToGroup failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.AddContactToGroupRequest](../../models/operations/addcontacttogrouprequest.md)                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.AddContactToGroupResponse](../../models/operations/addcontacttogroupresponse.md)\>**

### Errors

| Error Type               | Status Code              | Content Type             |
| ------------------------ | ------------------------ | ------------------------ |
| errors.ErrorResponse     | 404                      | application/json         |
| errors.ErrorResponse     | 400, 401, 403, 4XX       | application/problem+json |
| errors.ErrorResponse     | 5XX                      | application/problem+json |