# CURL queries

Some examples of running ES querie using CURL from the command line.

## Authentication

For local deployments it's common to run into Authentication issues when querying endpoints.

> note that from version 8 onwards, ES forces HTTPS

```console
curl -X GET https://localhost:9200
```

This will throw a cert error. When ES is initialised, certificates are created. So we need to specify them as part of our cURL command:

```console
curl --cacert config/certs/http_ca.crt -X GET https://localhost:9200
```

certificates are stored in `$ES_HOME/config/certs`.

This will still error with `missing authentication credentials for REST request`.

Requests must be authenticated. We can use the user and password for this:

```console
curl --cacert config/certs/http_ca.crt -u elastic -X GET https://localhost:9200
```

This will prompt for a p/w, but you can also add the password to the request like so:

```console
curl --cacert config/certs/http_ca.crt -u elastic:<your-pw> -X GET https://localhost:9200
```

It's better to set your password in the terminal as an environment variable:

```console
export ES_PW = "your-password"
curl --cacert config/certs/http_ca.crt -u elastic:$ES_PW -X GET https://localhost:9200
```

Check the variable has been included with `printenv`.

## Index search

Search an index (`products`) for all documents:

```console
 curl --cacert config/certs/http_ca.crt -u elastic:$ES_PW -X GET -H "Content-Type:application/json" https://localhost:9200/products/_search -d '{"query": { "match_all": { } }}'
```

the `-d` flag is for sending a body with the request in JSON form.


