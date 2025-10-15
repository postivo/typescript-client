# AddContactToGroupRequest

## Example Usage

```typescript
import { AddContactToGroupRequest } from "@postivo/postivo-client/models/operations";

let value: AddContactToGroupRequest = {
  id: 35,
  groupId: 656,
};
```

## Fields

| Field                                     | Type                                      | Required                                  | Description                               | Example                                   |
| ----------------------------------------- | ----------------------------------------- | ----------------------------------------- | ----------------------------------------- | ----------------------------------------- |
| `id`                                      | *number*                                  | :heavy_check_mark:                        | Global contact `id` to add to the group.  | 35                                        |
| `groupId`                                 | *number*                                  | :heavy_check_mark:                        | Group `id` to associate with the contact. | 656                                       |