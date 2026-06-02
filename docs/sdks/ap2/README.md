# Ap2

## Overview

Agent-to-Agent Payment Protocol

### Available Operations

* [ap2GetAgentCard](#ap2getagentcard) - Get the default agent card for AP2 payments
* [ap2ListPaymentMethods](#ap2listpaymentmethods) - List available payment methods for AP2
* [ap2CreateMandate](#ap2createmandate) - Create a spending mandate for recurring AP2 payments
* [ap2Execute](#ap2execute) - Execute a payment against an AP2 mandate
* [ap2ListMandates](#ap2listmandates) - List mandates for a card
* [ap2Settle](#ap2settle) - Settle an AP2 payment between agents

## ap2GetAgentCard

Get the default agent card for AP2 payments

### Example Usage

<!-- UsageSnippet language="typescript" operationID="ap2GetAgentCard" method="get" path="/api/ap2/agent-card" -->
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.ap2.ap2GetAgentCard();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { Mag3ntCore } from "@mag3nt/sdk/core.js";
import { ap2Ap2GetAgentCard } from "@mag3nt/sdk/funcs/ap2-ap2-get-agent-card.js";

// Use `Mag3ntCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const mag3nt = new Mag3ntCore({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const res = await ap2Ap2GetAgentCard(mag3nt);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("ap2Ap2GetAgentCard failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.Ap2GetAgentCardResponse](../../models/operations/ap2-get-agent-card-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.Mag3ntDefaultError | 4XX, 5XX                  | \*/\*                     |

## ap2ListPaymentMethods

List available payment methods for AP2

### Example Usage

<!-- UsageSnippet language="typescript" operationID="ap2ListPaymentMethods" method="post" path="/api/ap2/payment-methods" -->
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.ap2.ap2ListPaymentMethods();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { Mag3ntCore } from "@mag3nt/sdk/core.js";
import { ap2Ap2ListPaymentMethods } from "@mag3nt/sdk/funcs/ap2-ap2-list-payment-methods.js";

// Use `Mag3ntCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const mag3nt = new Mag3ntCore({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const res = await ap2Ap2ListPaymentMethods(mag3nt);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("ap2Ap2ListPaymentMethods failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.Ap2ListPaymentMethodsResponse](../../models/operations/ap2-list-payment-methods-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.Mag3ntDefaultError | 4XX, 5XX                  | \*/\*                     |

## ap2CreateMandate

Create a spending mandate for recurring AP2 payments

### Example Usage

<!-- UsageSnippet language="typescript" operationID="ap2CreateMandate" method="post" path="/api/ap2/mandate" -->
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.ap2.ap2CreateMandate({
    cardId: "<id>",
    cardToken: "<value>",
    amount: 1529.88,
    merchant: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { Mag3ntCore } from "@mag3nt/sdk/core.js";
import { ap2Ap2CreateMandate } from "@mag3nt/sdk/funcs/ap2-ap2-create-mandate.js";

// Use `Mag3ntCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const mag3nt = new Mag3ntCore({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const res = await ap2Ap2CreateMandate(mag3nt, {
    cardId: "<id>",
    cardToken: "<value>",
    amount: 1529.88,
    merchant: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("ap2Ap2CreateMandate failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.Ap2CreateMandateRequest](../../models/operations/ap2-create-mandate-request.md)                                                                                    | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.Ap2CreateMandateResponse](../../models/operations/ap2-create-mandate-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.Mag3ntDefaultError | 4XX, 5XX                  | \*/\*                     |

## ap2Execute

Execute a payment against an AP2 mandate

### Example Usage

<!-- UsageSnippet language="typescript" operationID="ap2Execute" method="post" path="/api/ap2/execute" -->
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.ap2.ap2Execute({
    cardId: "<id>",
    cardToken: "<value>",
    amount: "802.33",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { Mag3ntCore } from "@mag3nt/sdk/core.js";
import { ap2Ap2Execute } from "@mag3nt/sdk/funcs/ap2-ap2-execute.js";

// Use `Mag3ntCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const mag3nt = new Mag3ntCore({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const res = await ap2Ap2Execute(mag3nt, {
    cardId: "<id>",
    cardToken: "<value>",
    amount: "802.33",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("ap2Ap2Execute failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.Ap2ExecuteRequest](../../models/operations/ap2-execute-request.md)                                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.Ap2ExecuteResponse](../../models/operations/ap2-execute-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.Mag3ntDefaultError | 4XX, 5XX                  | \*/\*                     |

## ap2ListMandates

List mandates for a card

### Example Usage

<!-- UsageSnippet language="typescript" operationID="ap2ListMandates" method="get" path="/api/ap2/mandates/{card_id}" -->
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.ap2.ap2ListMandates("<id>");

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { Mag3ntCore } from "@mag3nt/sdk/core.js";
import { ap2Ap2ListMandates } from "@mag3nt/sdk/funcs/ap2-ap2-list-mandates.js";

// Use `Mag3ntCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const mag3nt = new Mag3ntCore({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const res = await ap2Ap2ListMandates(mag3nt, "<id>");
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("ap2Ap2ListMandates failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `cardId`                                                                                                                                                                       | *string*                                                                                                                                                                       | :heavy_check_mark:                                                                                                                                                             | N/A                                                                                                                                                                            |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.Ap2ListMandatesResponse](../../models/operations/ap2-list-mandates-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.Mag3ntDefaultError | 4XX, 5XX                  | \*/\*                     |

## ap2Settle

Completes a peer-to-peer payment between two agent cards. Debits the payer card and credits the receiver card atomically.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="ap2Settle" method="post" path="/api/ap2/settle" -->
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.ap2.ap2Settle({
    payerCardId: "<id>",
    payerCardToken: "<value>",
    receiverCardId: "<id>",
    amount: 5732.53,
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { Mag3ntCore } from "@mag3nt/sdk/core.js";
import { ap2Ap2Settle } from "@mag3nt/sdk/funcs/ap2-ap2-settle.js";

// Use `Mag3ntCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const mag3nt = new Mag3ntCore({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const res = await ap2Ap2Settle(mag3nt, {
    payerCardId: "<id>",
    payerCardToken: "<value>",
    receiverCardId: "<id>",
    amount: 5732.53,
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("ap2Ap2Settle failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.Ap2SettleRequest](../../models/operations/ap2-settle-request.md)                                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.Ap2SettleResponse](../../models/operations/ap2-settle-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 403                       | application/json          |
| errors.Mag3ntDefaultError | 4XX, 5XX                  | \*/\*                     |