# OpenRouter Setup & Configuration Guide

## Account Creation

1. Go to [openrouter.ai](https://openrouter.ai)
2. Click "Sign In" and create a free account (Google, GitHub, or email)
3. No credit card required for free models

## API Key Generation

1. Navigate to [openrouter.ai/keys](https://openrouter.ai/keys)
2. Click "Create Key"
3. Name it something identifiable (e.g., "Antigravity MCP Server")
4. Copy the key (starts with `sk-or-v1-`)
5. Store it securely -- it will not be shown again

## Rate Limits & Quotas

| Metric | Standard | After $10 Lifetime Spend |
|:---|:---|:---|
| Requests per minute | 20 | 20 |
| Requests per day | 50 | 1,000 |
| Cost per token | $0 | $0 |
| Max tokens per request | Model-dependent (typically 4096-8192) | Same |

## Free Model Details

### Recommended: `openrouter/free`
- This is a meta-model that auto-routes to the best available free model
- The underlying model may change day to day
- Supports text generation, code generation, and tool calling
- No token cost

### Alternative Free Models (as of Aug 2026)
These models may be available for free. Check [openrouter.ai/models](https://openrouter.ai/models) for current availability:

| Model | Strengths |
|:---|:---|
| NVIDIA Nemotron 3 Ultra (550B) | Large context, strong reasoning |
| NVIDIA Nemotron 3 Super | Good balance of speed and quality |
| Poolside Laguna S 2.1 | Code generation focused |
| InclusionAI Ling-3.0-flash | Fast inference |
| Cohere North Mini Code | Code-specific tasks |

## API Format

OpenRouter uses the **OpenAI-compatible API format**:

### Endpoint
```
POST https://openrouter.ai/api/v1/chat/completions
```

### Required Headers
```
Authorization: Bearer sk-or-v1-YOUR_KEY
Content-Type: application/json
HTTP-Referer: https://your-app-url.com (required by OpenRouter)
X-Title: Your App Name (optional but recommended)
```

### Request Body
```json
{
  "model": "openrouter/free",
  "messages": [
    { "role": "system", "content": "System prompt here" },
    { "role": "user", "content": "User message here" }
  ],
  "max_tokens": 4096,
  "temperature": 0.1
}
```

### Response Body
```json
{
  "id": "gen-...",
  "model": "actual-model-used",
  "choices": [
    {
      "message": {
        "role": "assistant",
        "content": "Generated content here"
      }
    }
  ],
  "usage": {
    "prompt_tokens": 150,
    "completion_tokens": 200,
    "total_tokens": 350
  }
}
```

## Error Codes

| HTTP Status | Meaning | Action |
|:---|:---|:---|
| 200 | Success | Process response |
| 401 | Invalid API key | Check/regenerate key |
| 402 | Quota exceeded | Wait until tomorrow or add credits |
| 429 | Rate limit (20 req/min) | Retry after delay (auto-handled by server) |
| 500+ | Server error | Retry with backoff (auto-handled by server) |

## Configuration Locations

### MCP Server .env file
```
C:\Users\Vijay Pai\openrouter-mcp-server\.env
```

### Antigravity MCP Config (alternative location for API key)
```
C:\Users\Vijay Pai\.gemini\config\mcp_config.json
```
The API key can be set in either location. The `mcp_config.json` env takes precedence.

## Monitoring Usage

1. Go to [openrouter.ai/activity](https://openrouter.ai/activity)
2. View request count, token usage, and model routing
3. Track daily quota consumption
