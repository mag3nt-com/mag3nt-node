# Environment

'sandbox' for testnet networks (e.g. eip155:84532), 'production' for mainnet. Sandbox transactions deduct balance but are never settled on-chain.

## Example Usage

```typescript
import { Environment } from "@mag3nt/sdk/models/operations";

let value: Environment = "production";

// Open enum: unrecognized values are captured as Unrecognized<string>
```

## Values

```typescript
"sandbox" | "production" | Unrecognized<string>
```