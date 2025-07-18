# Debugging Elasticsearch

This isn't part of the course, but we'll use this section to document various debugging session during the course.

## Kibana cannot connect to Elasticsearch

I ran into this error while trying to startup Kibana for the second time:

```console
[elasticsearch-service] Unable to retrieve version information from Elasticsearch nodes. Request timed out
```

This suggests Kibana cannot connect to ES.

Firt check if ES is running:

```console
curl localhost:9200/
```

If there is an empty response, it means Debugging
