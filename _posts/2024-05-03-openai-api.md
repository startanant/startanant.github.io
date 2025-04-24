
---
layout: post
title:  "API Documentation: OpenAI API"
date:   2024-05-03 17:33:46 -0400
categories: tech
tags: json api openai programming
---

## OpenAI API – Access GPT Models (Chat, Completion, Embeddings)

The OpenAI API provides access to powerful AI models like GPT-4 and GPT-3.5 for tasks such as natural language processing, code generation, summarization, chatbots, and more.

---
<br><br>
## 🔗 Base URL

```
https://api.openai.com/v1/
```

---
<br><br>
##  Authentication

You’ll need an API key from your OpenAI account.  
 [Get your API key here](https://platform.openai.com/account/api-keys)

Add the key to the `Authorization` header:

```
Authorization: Bearer YOUR_API_KEY
```

---
<br><br>
## Popular Endpoints

### 💬 1. Chat Completions (GPT-4, GPT-3.5)

**Endpoint:**

```
POST /chat/completions
```

**Example Request:**

```json
{
  "model": "gpt-4",
  "messages": [
    { "role": "user", "content": "Tell me a joke about AI." }
  ]
}
```

**cURL:**

```bash
curl https://api.openai.com/v1/chat/completions \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "gpt-4",
    "messages": [{"role": "user", "content": "Tell me a joke about AI."}]
  }'
```

---
<br><br>
###  2. Text Completions

**Endpoint:**

```
POST /completions
```

**Example Request:**

```json
{
  "model": "text-davinci-003",
  "prompt": "Write a haiku about the moon.",
  "max_tokens": 50
}
```

---
<br><br>
###  3. Embeddings

**Endpoint:**

```
POST /embeddings
```

**Example Request:**

```json
{
  "model": "text-embedding-ada-002",
  "input": "AI is transforming the world."
}
```

---
<br><br>
##  Pricing (As of 2024)

| Model               | Price per 1K tokens (Input) | Price per 1K tokens (Output) |
|--------------------|-----------------------------|------------------------------|
| GPT-4 (8K context)  | $0.03                       | $0.06                        |
| GPT-3.5 (Turbo)     | $0.0015                     | $0.002                       |
| Embeddings (Ada-002)| $0.0001                     | N/A                          |

 [View full pricing](https://openai.com/pricing)

---
<br><br>
##  Libraries & SDKs

- **Node.js**: `openai`
- **Python**: `openai`
- **Others**: Community SDKs for Go, Ruby, Java, etc.

 [OpenAI API Reference](https://platform.openai.com/docs)

---
<br><br>
## ⚠️ Rate Limits

Rate limits depend on the model and plan. For example:
- Free trial accounts: limited quota
- Paid plans: higher throughput

[Check usage dashboard](https://platform.openai.com/account/usage)

---
