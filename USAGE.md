<!-- Start SDK Example Usage [usage] -->
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.cards.cardsList();

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->