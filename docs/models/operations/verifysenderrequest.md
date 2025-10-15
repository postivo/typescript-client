# VerifySenderRequest

## Example Usage

```typescript
import { VerifySenderRequest } from "@postivo/postivo-client/models/operations";

let value: VerifySenderRequest = {
  id: 443,
  requestBody: {
    verificationCode: "A345FP73",
  },
};
```

## Fields

| Field                                                                                    | Type                                                                                     | Required                                                                                 | Description                                                                              | Example                                                                                  |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `id`                                                                                     | *number*                                                                                 | :heavy_check_mark:                                                                       | ID of the sender to verify.                                                              | 443                                                                                      |
| `requestBody`                                                                            | [operations.VerifySenderRequestBody](../../models/operations/verifysenderrequestbody.md) | :heavy_check_mark:                                                                       | Verification code received in the letter.                                                |                                                                                          |