# XMag3ntEnvironment

'sandbox' for testnet networks, 'production' for mainnet

## Example Usage

```typescript
import { XMag3ntEnvironment } from "@mag3nt/sdk/models/components";

let value: XMag3ntEnvironment = "production";

// Open enum: unrecognized values are captured as Unrecognized<string>
```

## Values

```typescript
"sandbox" | "production" | Unrecognized<string>
```