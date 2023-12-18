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
  --url http://127.0.0.1:4010/api/v1/conversations/123e4567-e89b-12d3-a456-426614174000 \
  --header 'Accept: application/json' \
  --header 'Authorization: Bearer 123-sekret' 

## Response
{
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "messages": [
    {
      "created_at": 1702494381,
      "role": "assistant",
      "content": [
        {
          "type": "text",
          "text": {
            "value": "Honeyed tea of course",
            "annotations": [
              {
                "type": "citation",
                "rank": 1,
                "text": "The brilliant cure-all, Honeyed tea",
                "href": "https://www.expertdomain.com/health/cold-flu/honey-lemon-tea"
              }
            ]
          }
        }
      ]
    }
  ]
}
```