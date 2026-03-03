# AWS Bedrock Support

This fork adds AWS Bedrock as an LLM provider using Bearer Token authentication.

## Configuration

Set the following environment variables:

| Variable | Description |
|---|---|
| `LLM` | Set to `bedrock` |
| `AWS_BEARER_TOKEN_BEDROCK` | Your AWS Bedrock API key (Bearer Token) |
| `AWS_REGION` | AWS region (default: `us-east-1`) |
| `BEDROCK_MODEL` | Model ID (e.g. `global.anthropic.claude-opus-4-6-v1`) |

### Docker example

```bash
docker run -it --name presenton -p 5000:80 \
  -e LLM="bedrock" \
  -e AWS_BEARER_TOKEN_BEDROCK="your-bearer-token" \
  -e AWS_REGION="us-east-1" \
  -e BEDROCK_MODEL="global.anthropic.claude-opus-4-6-v1" \
  -e IMAGE_PROVIDER="pexels" \
  -e PEXELS_API_KEY="your-pexels-key" \
  -v "./app_data:/app_data" \
  ghcr.io/presenton/presenton:latest
```

## Keeping up with upstream

This fork tracks `presenton/presenton` as `upstream`. To pull in upstream changes:

```bash
git fetch upstream
git checkout main
git merge upstream/main
git checkout feat/bedrock
git rebase main
git push origin feat/bedrock --force-with-lease
```
