# PingResponse

Ping response.

## Example Usage

```typescript
import { PingResponse } from "@postivo/postivo-client/models";

let value: PingResponse = {
  status: "OK",
  version: "1.0",
  sandbox: false,
};
```

## Fields

| Field                                                                          | Type                                                                           | Required                                                                       | Description                                                                    | Example                                                                        |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `status`                                                                       | *string*                                                                       | :heavy_minus_sign:                                                             | API service status: OK (available), ERR (unavailable).                         | OK                                                                             |
| `version`                                                                      | *string*                                                                       | :heavy_minus_sign:                                                             | Current API version.                                                           | 1.0                                                                            |
| `sandbox`                                                                      | *boolean*                                                                      | :heavy_minus_sign:                                                             | Indicates whether the connection was established to the test system (SANDBOX). | false                                                                          |