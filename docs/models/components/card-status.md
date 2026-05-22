# CardStatus

## Example Usage

```typescript
import { CardStatus } from "@mag3nt/sdk/models/components";

let value: CardStatus = "ACTIVE";

// Open enum: unrecognized values are captured as Unrecognized<string>
```

## Values

```typescript
"ACTIVE" | "FROZEN" | "EXPIRED" | "USED" | "PENDING_FUNDING" | "FUNDING_FAILED" | Unrecognized<string>
```