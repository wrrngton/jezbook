# Certbot

This program allows you to generate SSL certificates and assign them to domains.

Generate SSL certificates for all/selected domains:

```console
$ certbot --nginx
```

For specific domains

```console
$ certbot --nginx -d domain1.com
```
For multiple domains

```console
$ certbot --nginx -d domain1.com -d domain2.com
```
