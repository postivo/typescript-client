# RemoveContactByExtIdToGroupRequest

## Example Usage

```typescript
import { RemoveContactByExtIdToGroupRequest } from "@postivo/postivo-client/models/operations";

let value: RemoveContactByExtIdToGroupRequest = {
  extId: "my-id-1",
  groupId: 656,
};
```

## Fields

| Field                                                         | Type                                                          | Required                                                      | Description                                                   | Example                                                       |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| `extId`                                                       | *string*                                                      | :heavy_check_mark:                                            | External (custom) ID of the contact to detach from the group. | my-id-1                                                       |
| `groupId`                                                     | *number*                                                      | :heavy_check_mark:                                            | Group `id` to detach from the contact.                        | 656                                                           |