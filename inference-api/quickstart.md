---
description: >-
  Our trained planning models will be available via API, allowing you to
  integrate sophisticated computer-control AI into your applications.
---

# 🤖 Deploy Agentic AI with $VIRAL

Stay tuned!

## Authentication

All API calls require payment in $VIRAL tokens. You'll need to:

1. Hold $VIRAL in your connected wallet
2. Include your wallet address in the authentication header
3. Sign API requests using your wallet

### Endpoints

`POST https://api.viralmind/v1/plan` **( Coming soon )**

```json
{
  "goal": "Order a pepperoni pizza from Dominos",
  "current_state": {
    "messages": [],
    "screenshot": "<base64 encoded>",
    "viewport": {
      "width": 1920,
      "height": 1080
    }
  },
  "max_steps": 10
}
```

#### Response Format

```json
{
  "plan": [
    {
      "action": "click",
      "target": "Order Online button",
      "coordinates": [245, 123]
    },
    {
      "action": "type",
      "text": "pepperoni",
      "target": "search field"
    },
    // Additional steps...
  ],
  "estimated_cost": "0.05 $VIRAL"
}
```
