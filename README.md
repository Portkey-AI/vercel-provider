# Vercel AI SDK - Portkey Provider

The **[Portkey provider](https://sdk.vercel.ai/providers/community-providers/portkey)** for the [Vercel AI SDK](https://sdk.vercel.ai/docs)
contains language model support for the Portkey chat and completion APIs.

## Setup

The Portkey provider is available in the `portkey-ai-provider` module. You can install it with

```bash
pnpm add portkey-ai-provider
```

### Provider and Model

```ts
import { createPortkey } from '@ai-sdk/portkey'
const llmClient = createPortkey(
  {
    apiKey: {{PORTKEY_API_KEY}},
    config: {{PORTKEY_CONFIG_ID}},
  }
)
```

## Example

```ts
  const response = await generateText({
    model: llmClient.chatModel({{MODEL_ID}}),
    messages: [
      {
        role: "user",
        content: "What is a portkey?"
      }
    ],
    maxTokens: 40
  })

console.log(response)
```

## Image generation example

```ts
const response = await generateImage({
  model: llmClient.imageModel(model),
  prompt:
    "A playful dog riding a skateboard, showcasing a fun and energetic vibe. The dog is a medium-sized breed with a joyful expression, wearing a colorful bandana.",
  n: 1,
  size: "1024x1024" as `${number}x${number}`,
  aspectRatio: "1:1" as `${number}:${number}`,
});
```

response.images returned by the `generateImage` method is either an array of base64 strings or an array of bytes (Uint8Array).

## Documentation

Please check out the **[Portkey provider documentation](https://docs.portkey.ai/docs/integrations/libraries/vercel)** for more information.
