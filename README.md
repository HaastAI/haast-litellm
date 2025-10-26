# Haast LiteLLM Proxy Server
## Quick Start
### Env File
```
#.env
LITELLM_MASTER_KEY=
LITELLM_SALT_KEY=
ANTHROPIC_API_KEY=
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_REGION_NAME=
```
### Start server
`docker compose up`

### Generate a LiteLLM API Key
```
curl -X POST "http://0.0.0.0:4000/key/generate" -H "Authorization: Bearer <master key>" -H "Content-Type: application/json" -d '{}'
```

### Generate a Chat Completion
```
curl -X POST "http://0.0.0.0:4000/chat/completions" -H "Authorization: Bearer <generated key> -H "Content-Type: application/json" -d '{
    "model": "claude-3.7",
    "messages": [
        {
            "role": "user",
            "content": "this is a test request, write a short poem"
        }
    ]
}'
```
