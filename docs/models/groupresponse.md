# GroupResponse

Address Book group details returned by the API.

## Example Usage

```typescript
import { GroupResponse } from "@postivo/postivo-client/models";

let value: GroupResponse = {
  name: "my-group",
  description: "This is a group for school contacts",
  id: 234,
};
```

## Fields

| Field                               | Type                                | Required                            | Description                         | Example                             |
| ----------------------------------- | ----------------------------------- | ----------------------------------- | ----------------------------------- | ----------------------------------- |
| `name`                              | *string*                            | :heavy_check_mark:                  | Group name.                         | my-group                            |
| `description`                       | *string*                            | :heavy_minus_sign:                  | Optional group description.         | This is a group for school contacts |
| `id`                                | *number*                            | :heavy_check_mark:                  | Unique system-assigned group ID.    | 234                                 |