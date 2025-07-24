# Elasticsearch

[relevant docs](https://www.elastic.co/docs/solutions/search)

This course focuses solely on Elasticsearch, not the total ELK stack (Elastic, Logstash, Kibana).

## What is ElasticSearch?

Elasticsearch is an open source analytics and search engine. 

Some use cases include:

- Full text search across a product catalogue
- Querying and analysing structures data such as logs or analytics
- Application Performance Management (APM) is a specific use case where you store logs in Elastic and visualise them to monitor application performance (such as a CPU/RAM) 
- Send events to ElasticSearch. E.g send sales from physical stores to ElasticSearch

ES is written in **Java** and is build ontop of **Apache Lucene**.

## How does Elasticsearch work?

Data is stored as documents in ES. A document represents a row in a database and contains fields similar to columns in relational databases.

A document is just a JSON document.

To query these documents we just use a REST API. The query and the document are both JSON objects.
