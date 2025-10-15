# GetAccountDetailsResponse


## Supported Types

### `models.AccountResponse`

```typescript
const value: models.AccountResponse = {
  login: "some_login",
  accountType: "PRE-PAID",
  limit: 0,
  credit: 130.44,
  subcredit: 65.32,
  currency: "PLN",
  name: "Andrzej Nowak",
  isMain: true,
};
```

### `models.ErrorResponse`

```typescript
const value: models.ErrorResponse = {
  type: "https://problems-registry.smartbear.com/invalid-body-property-format",
  status: 400,
  title: "Invalid Body property format",
  detail: "The request body contains a malformed property",
  code: "400-21",
  instance: "/rest/messages/sms",
};
```

