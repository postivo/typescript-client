# RecipientFromAddressBookByExternalId

Select shipment recipient data from the Address Book by external (custom) ID.

## Example Usage

```typescript
import { RecipientFromAddressBookByExternalId } from "@postivo/postivo-client/models";

let value: RecipientFromAddressBookByExternalId = {
  extId: "marcin-344",
  fromShared: true,
  customId: "my-id-1113",
  postscript: "Do rąk własnych",
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   | Example                                                                                       |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `extId`                                                                                       | *string*                                                                                      | :heavy_check_mark:                                                                            | External (custom) ID of the recipient stored in your Address Book.                            | marcin-344                                                                                    |
| `fromShared`                                                                                  | *boolean*                                                                                     | :heavy_minus_sign:                                                                            | Set to true to fetch recipient data by external ID from a main account’s shared Address Book. | true                                                                                          |
| `customId`                                                                                    | *string*                                                                                      | :heavy_minus_sign:                                                                            | Custom shipment ID assigned by the user.                                                      | my-id-1113                                                                                    |
| `postscript`                                                                                  | *string*                                                                                      | :heavy_minus_sign:                                                                            | Optional postscript printed above the recipient data on the envelope.                         | Do rąk własnych                                                                               |