# StatusEvent

Single shipment status event.

## Example Usage

```typescript
import { StatusEvent } from "@postivo/postivo-client/models";

let value: StatusEvent = {
  uniqueId: 778656,
  type: "OK",
  code: "ACCEPTED",
  name: "Przesyłka przyjęta do realizacji",
  details: "Przyjęcie do Punktu Dystrybucyjnego",
  date: new Date("2024-06-01T12:00:00Z"),
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   | Example                                                                                       |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `uniqueId`                                                                                    | *number*                                                                                      | :heavy_minus_sign:                                                                            | Unique status event ID.                                                                       | 778656                                                                                        |
| `type`                                                                                        | *string*                                                                                      | :heavy_minus_sign:                                                                            | Event type: `OK` (regular) or `EX` (exception/irregular).                                     | OK                                                                                            |
| `code`                                                                                        | *string*                                                                                      | :heavy_minus_sign:                                                                            | Status event code.                                                                            | ACCEPTED                                                                                      |
| `name`                                                                                        | *string*                                                                                      | :heavy_minus_sign:                                                                            | Status event description.                                                                     | Przesyłka przyjęta do realizacji                                                              |
| `details`                                                                                     | *string*                                                                                      | :heavy_minus_sign:                                                                            | Status event details (for EXTERNAL status codes).                                             | Przyjęcie do Punktu Dystrybucyjnego                                                           |
| `date`                                                                                        | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_minus_sign:                                                                            | Status event timestamp (UTC).                                                                 | 2024-06-01T12:00:00Z                                                                          |