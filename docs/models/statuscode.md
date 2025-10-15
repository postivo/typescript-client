# StatusCode

## Example Usage

```typescript
import { StatusCode } from "@postivo/postivo-client/models";

let value: StatusCode = {
  code: "ACCEPTED",
  name: "Przesyłka przyjęta do realizacji",
  description:
    "Przesyłka została poprawnie zapisana w bazie i będzie procesowana zgodnie z parametrami.",
};
```

## Fields

| Field                                                                                    | Type                                                                                     | Required                                                                                 | Description                                                                              | Example                                                                                  |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `code`                                                                                   | *string*                                                                                 | :heavy_minus_sign:                                                                       | Unique status code.                                                                      | ACCEPTED                                                                                 |
| `name`                                                                                   | *string*                                                                                 | :heavy_minus_sign:                                                                       | Status name.                                                                             | Przesyłka przyjęta do realizacji                                                         |
| `description`                                                                            | *string*                                                                                 | :heavy_minus_sign:                                                                       | Status description.                                                                      | Przesyłka została poprawnie zapisana w bazie i będzie procesowana zgodnie z parametrami. |