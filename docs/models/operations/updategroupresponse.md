# UpdateGroupResponse

## Example Usage

```typescript
import { UpdateGroupResponse } from "@postivo/postivo-client/models/operations";

let value: UpdateGroupResponse = {
  headers: {
    "key": [
      "<value 1>",
    ],
  },
  result: {
    name: "my-group",
    description: "This is a group for school contacts",
    id: 234,
    inherited: false,
  },
};
```

## Fields

| Field                                  | Type                                   | Required                               | Description                            |
| -------------------------------------- | -------------------------------------- | -------------------------------------- | -------------------------------------- |
| `headers`                              | Record<string, *string*[]>             | :heavy_check_mark:                     | N/A                                    |
| `result`                               | *operations.UpdateGroupResponseResult* | :heavy_check_mark:                     | N/A                                    |