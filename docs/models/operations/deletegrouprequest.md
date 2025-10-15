# DeleteGroupRequest

## Example Usage

```typescript
import { DeleteGroupRequest } from "@postivo/postivo-client/models/operations";

let value: DeleteGroupRequest = {
  id: 876,
};
```

## Fields

| Field                                                                    | Type                                                                     | Required                                                                 | Description                                                              | Example                                                                  |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `id`                                                                     | *number*                                                                 | :heavy_check_mark:                                                       | Group `id` to remove.                                                    | 876                                                                      |
| `contacts`                                                               | [operations.ContactHandling](../../models/operations/contacthandling.md) | :heavy_minus_sign:                                                       | How to handle contacts that belong to the group.                         |                                                                          |