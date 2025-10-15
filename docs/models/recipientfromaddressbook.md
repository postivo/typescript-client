# RecipientFromAddressBook

Select recipient data for a shipment from the Address Book.

## Example Usage

```typescript
import { RecipientFromAddressBook } from "@postivo/postivo-client/models";

let value: RecipientFromAddressBook = {
  id: 344,
  customId: "my-id-1113",
  postscript: "Do rąk własnych",
};
```

## Fields

| Field                                                                 | Type                                                                  | Required                                                              | Description                                                           | Example                                                               |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `id`                                                                  | *number*                                                              | :heavy_check_mark:                                                    | Global ID of the recipient stored in the personal Address Book.       | 344                                                                   |
| `customId`                                                            | *string*                                                              | :heavy_minus_sign:                                                    | User-assigned custom shipment ID.                                     | my-id-1113                                                            |
| `postscript`                                                          | *string*                                                              | :heavy_minus_sign:                                                    | Optional postscript printed above the recipient data on the envelope. | Do rąk własnych                                                       |