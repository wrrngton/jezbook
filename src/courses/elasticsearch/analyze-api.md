# Analyze API

[API docs](https://www.elastic.co/docs/api/doc/elasticsearch/operation/operation-indices-analyze)

The analyze API allows us to:

1. Build custom analyzers
2. Inspect what ES analysis is doing under the hood

## Analyze text

```
POST /_analyze
{
    "text": "2 guys walk into  a bar, but the third... DUCKS!:-)",
    "analyzer": "standard"
}
```

**Response**:
```
{
  "tokens": [
    {
      "token": "2",
      "start_offset": 0,
      "end_offset": 1,
      "type": "<NUM>",
      "position": 0
    },
    {
      "token": "guys",
      "start_offset": 2,
      "end_offset": 6,
      "type": "<ALPHANUM>",
      "position": 1
    },
    {
      "token": "walk",
      "start_offset": 7,
      "end_offset": 11,
      "type": "<ALPHANUM>",
      "position": 2
    },
    {
      "token": "into",
      "start_offset": 12,
      "end_offset": 16,
      "type": "<ALPHANUM>",
      "position": 3
    },
    {
      "token": "a",
      "start_offset": 18,
      "end_offset": 19,
      "type": "<ALPHANUM>",
      "position": 4
    },
    {
      "token": "bar",
      "start_offset": 20,
      "end_offset": 23,
      "type": "<ALPHANUM>",
      "position": 5
    },
    {
      "token": "but",
      "start_offset": 25,
      "end_offset": 28,
      "type": "<ALPHANUM>",
      "position": 6
    },
    {
      "token": "the",
      "start_offset": 29,
      "end_offset": 32,
      "type": "<ALPHANUM>",
      "position": 7
    },
    {
      "token": "third",
      "start_offset": 33,
      "end_offset": 38,
      "type": "<ALPHANUM>",
      "position": 8
    },
    {
      "token": "ducks",
      "start_offset": 42,
      "end_offset": 47,
      "type": "<ALPHANUM>",
      "position": 9
    }
  ]
}
```

Under the hood, the `analyzer` parameter is comprised of 3 components:

- `char_filter`
- `tokenizer`
- `filter`

ES exposes these to us so we can build our own custom analyzers. See more [here](https://www.elastic.co/docs/manage-data/data-store/text-analysis/create-custom-analyzer)
