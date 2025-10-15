# AddContactByExtIdToGroupRequest

## Example Usage

```typescript
import { AddContactByExtIdToGroupRequest } from "@postivo/postivo-client/models/operations";

let value: AddContactByExtIdToGroupRequest = {
  extId: "my-id-1",
  groupId: 656,
};
```

## Fields

| Field                                                    | Type                                                     | Required                                                 | Description                                              | Example                                                  |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `extId`                                                  | *string*                                                 | :heavy_check_mark:                                       | External (custom) ID of the contact to add to the group. | my-id-1                                                  |
| `groupId`                                                | *number*                                                 | :heavy_check_mark:                                       | Group `id` to associate with the contact.                | 656                                                      |