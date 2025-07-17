# Elastic stack 

## ELK stack

The Elastic Stack refers to all the products within the Elastic offering.

This three core componets of this are:

- **E**lasticsearch: the core of Elastic
- **L**ogstash: an events processing pipeline 
- **K**Kibana: data visualisation tool

This is commonly referred to as the ELK stack. However, there is more to Elastic and the ELK stack is common parlance as these three tools are often used together.

## Elastic stack

The true Elastic stack has more offerings, however, including:

- **Beats**: used for data ingestion, it sends data to Logstach or Elasticsearch
- **X-Pack**: a set of ES extensions that adds auth, security, alterting and ML capabilities

> The Elastic stack is a superset of the ELK stack

Put loosely, 

1. Beats and logstash are used for data ingestion
2. ElasticSearch searches analyzes and stores data
3. Kibana visualises data
4. X-pack adds features to the stack
