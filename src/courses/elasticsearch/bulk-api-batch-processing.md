# The Bulk API and batch processing

[API docs](https://www.elastic.co/docs/api/doc/elasticsearch/operation/operation-bulk)

The bulk API lets you run bulk operations on indices at once. The API uses `NDJSON`, which follows this convention:

- Operation on first line
- Request body on subsequent line
- Additional operations on next line and so on...

When using bulk ensure to:

- Set `Content-Type: application/x-ndjson`
- Each line must end with new line or new line character: `\n` or `\r\n` **including the last line!**
- If a single action fails, the other actions will proceed as normal
- Include [optimistic concurrency control](/optimistic-concurrency-control.md) parameters as it's supported in the Bulk API

> The Bulk API is useful when you have many write actions to perform at once, it is more performant as it reduces network round trips

> It's useful for scripted updates, e.g loading large amounts of data

## Batch index data

```
POST /_bulk
{"index": { "_index": "products", "_id": 200 }}
{ "name": "Espresso Machine", "price": 199, "in_stock": 5 }
{"create": { "_index": "products", "_id": 201 }}
{ "name": "Milk frother", "price": 149, "in_stock":  14}
```

## Update and delete docs

```
POST /_bulk
{"update": {"_index": "products", "_id": 201}}
{"doc": {"price": 129}}
{"delete": {"_index": "products", "_id": 200}}
```

## Target single index

If all your bulk operations are on the same index you can specify the index in the request endpoint:

```
POST /products/_bulk
{"update": {"_id": 201}}
{"doc": {"price": 129}}
{"delete": {"_id": 200}}
```



