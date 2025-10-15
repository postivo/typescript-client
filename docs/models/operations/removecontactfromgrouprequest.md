# RemoveContactFromGroupRequest

## Example Usage

```typescript
import { RemoveContactFromGroupRequest } from "@postivo/postivo-client/models/operations";

let value: RemoveContactFromGroupRequest = {
  id: 35,
  groupId: 656,
};
```

## Fields

| Field                                         | Type                                          | Required                                      | Description                                   | Example                                       |
| --------------------------------------------- | --------------------------------------------- | --------------------------------------------- | --------------------------------------------- | --------------------------------------------- |
| `id`                                          | *number*                                      | :heavy_check_mark:                            | Global contact `id` to detach from the group. | 35                                            |
| `groupId`                                     | *number*                                      | :heavy_check_mark:                            | Group `id` to detach from the contact.        | 656                                           |