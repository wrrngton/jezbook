# Hosting options

There are a few hosting options:

## Elastic/Opensearch on Bonsai or another hosted service

Offerings like [Bonsai](http://bonsai.io/) will manage your ES cluster for you

## Elastic Cloud

This is ES's native offering and lets ES manage your deployment for you. 

## Elastic serverless

ES also have a serverless option. This offering autoscales and is stateless and is optimised for *realtime applications*.

It eliminates the need for node and shard management, capacity planning etc by decoupling compute from storagfe and indexing from search.

## Self hosting

You can also self host ES on your own machines. You can download ES [here](https://www.elastic.co/downloads/elasticsearch?pg=global&plcmt=nav&cta=205352-title).

It will download two archives, one for ES and one for Kibana in separate directories.

It ships with dependencies like Java(ES) and Node.js (Kibana).

