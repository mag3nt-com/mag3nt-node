# Payments

## Overview

Universal outbound protocol payments

### Available Operations

* [paymentsExecute](#paymentsexecute) - Execute a universal outbound payment

## paymentsExecute

Enables any mag3nt card to pay any external x402, MPP, or AP2 endpoint in a single HTTP call. The engine automatically probes the target URL, detects the protocol, and settles on-chain.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="paymentsExecute" method="post" path="/api/pay" -->
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.payments.paymentsExecute({
    cardId: "sx_a66a6666-...",
    cardToken: "tok_3b9fe670-...",
    url: "https://api.weather.com/forecast",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { Mag3ntCore } from "@mag3nt/sdk/core.js";
import { paymentsPaymentsExecute } from "@mag3nt/sdk/funcs/payments-payments-execute.js";

// Use `Mag3ntCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const mag3nt = new Mag3ntCore({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const res = await paymentsPaymentsExecute(mag3nt, {
    cardId: "sx_a66a6666-...",
    cardToken: "tok_3b9fe670-...",
    url: "https://api.weather.com/forecast",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("paymentsPaymentsExecute failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.PaymentsExecuteRequest](../../models/operations/payments-execute-request.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.PaymentsExecuteResponse](../../models/operations/payments-execute-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.Mag3ntDefaultError | 4XX, 5XX                  | \*/\*                     |