# DocumentMock

Mock document used to simulate page count for pricing without uploading a real file.

## Example Usage

```typescript
import { DocumentMock } from "@postivo/postivo-client/models";

let value: DocumentMock = {
  pages: 3,
};
```

## Fields

| Field                                 | Type                                  | Required                              | Description                           | Example                               |
| ------------------------------------- | ------------------------------------- | ------------------------------------- | ------------------------------------- | ------------------------------------- |
| `pages`                               | *number*                              | :heavy_check_mark:                    | Number of pages in the mock document. | 3                                     |