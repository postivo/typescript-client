# Group

Contact group definition in the Address Book.

## Example Usage

```typescript
import { Group } from "@postivo/postivo-client/models";

let value: Group = {
  name: "my-group",
  description: "This is a group for school contacts",
};
```

## Fields

| Field                               | Type                                | Required                            | Description                         | Example                             |
| ----------------------------------- | ----------------------------------- | ----------------------------------- | ----------------------------------- | ----------------------------------- |
| `name`                              | *string*                            | :heavy_check_mark:                  | Group name.                         | my-group                            |
| `description`                       | *string*                            | :heavy_minus_sign:                  | Optional group description.         | This is a group for school contacts |