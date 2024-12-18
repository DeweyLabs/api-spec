# Dewey API Spec

## Viewing the API Docs

```bash
npm install -g @redocly/cli@latest
redocly preview-docs openapi_spec.yml
# open http://127.0.0.1:8080 to view
```

## Setting up a mock server to develop against

```bash
npm install -g @stoplight/prism-cli

prism mock openapi_spec.yml

# Basic Request

curl --request GET \
  --url http://127.0.0.1:4010/api/v0/questions/trending \
  --header 'Accept: application/json' \
  --header 'X-Dewey-Key: pk_test_123abc' 

## Response
{
  "questions": [
    "What is the best way to get rid of a cold?"
  ]
}
```