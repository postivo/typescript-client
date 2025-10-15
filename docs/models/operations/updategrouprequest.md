# UpdateGroupRequest

## Example Usage

```typescript
import { UpdateGroupRequest } from "@postivo/postivo-client/models/operations";

let value: UpdateGroupRequest = {
  id: 14,
  group: {
    name: "my-group",
    description: "This is a group for school contacts",
  },
};
```

## Fields

| Field                                     | Type                                      | Required                                  | Description                               | Example                                   |
| ----------------------------------------- | ----------------------------------------- | ----------------------------------------- | ----------------------------------------- | ----------------------------------------- |
| `id`                                      | *number*                                  | :heavy_check_mark:                        | Group `id` to update.                     | 14                                        |
| `group`                                   | [models.Group](../../models/group.md)     | :heavy_check_mark:                        | A `Group` object with the updated fields. |                                           |