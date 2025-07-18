# Useful Elastic command

## Remove Mac gatekeeper signature from .tar download

```console
xattr -r -d com.apple.quarantine <elastic-path>
```

## Extract kibana and ES .tar archives

```console
tar -xvf <path>
```

## Reset `elastic` user password

```console
bin/elasticsearch-reset-password -u elastic
```

## Generate new Kibana token

```console
bin/elasticsearch-create-enrollment-token --scope kibana
```
